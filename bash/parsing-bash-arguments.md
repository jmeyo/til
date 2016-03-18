# Using Modern getopt For Shell Argument Parsing

The modern getopt from glibc/util-linux has full backwards compatibility with the old getopt from C, works with all option types (long, short, and with equal signs) and exists just about everywhere. Also, handily, you can test for its existence to make sure you remain portable (AKA fail when you're on something so old it shouldn't exist anymore).

    #!/bin/bash
    
    getopt --test > /dev/null
    if [[ $? != 4 ]]; then
        echo "I’m sorry, `getopt --test` failed in this environment."
        exit 1
    fi
    
    SHORT=dfo:v
    LONG=debug,force,output:,verbose

    PARSED=`getopt --options $SHORT --longoptions $LONG --name "$0" -- "$@"`
    if [[ $? != 0 ]]; then
        exit 2
    fi
    eval set -- "$PARSED"
    
    while true; do
        case "$1" in
            -d|--debug)
                d=y
                shift
                ;;
            -f|--force)
                f=y
                shift
                ;;
            -v|--verbose)
                v=y
                shift
                ;;
            -o|--output)
                outFile="$2"
                shift 2
                ;;
            --)
                shift
                break
                ;;
            *)
                echo "Programming error"
                exit 3
                ;;
        esac
    done
    
    if [[ $# != 1 ]]; then
        echo "$0: A single input file is required."
        exit 4
    fi

    echo "verbose: $v, force: $f, debug: $d, in: $1, out: $outFile"

Discovered and taken from Robert Siemer's [StackOverflow Answer](http://stackoverflow.com/a/29754866).
