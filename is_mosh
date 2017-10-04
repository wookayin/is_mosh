#!/bin/bash

has_ancestor_mosh() {
    pstree -ps $1 | grep mosh-server
}

is_mosh() {
    # argument handling
    for arg in "$@"; do
        case $arg in
          -v|--verbose) local VERBOSE=YES ;;
          *) ;;
        esac
    done

    if [[ -n "$TMUX" ]]; then
        # current shell is under tmux
        local tmux_current_session=$(tmux display-message -p '#S')
        local tmux_client_id=$(tmux list-clients -t "${tmux_current_session}" -F '#{client_pid}')
        # echo $tmux_current_session $tmux_client_id
        local pid="$tmux_client_id"
    else
        local pid="$$"
    fi

    local mosh_found=$(has_ancestor_mosh $pid)   # or empty if not found
    if [[ -z "$mosh_found" ]]; then
        return 1;    # exit code 1: not mosh
    fi

    test -n "$VERBOSE" && echo "mosh"
    return 0;        # exit code 0: is mosh
}


sourced=0
if [ -n "$ZSH_EVAL_CONTEXT" ]; then
  case $ZSH_EVAL_CONTEXT in *:file) sourced=1;; esac
elif [ -n "$BASH_VERSION" ]; then
  [ "$0" != "$BASH_SOURCE" ] && sourced=1
else
  case ${0##*/} in sh|dash) sourced=1;; esac
fi
if [[ $sourced == 0 ]]; then
  is_mosh $@
fi
