# Locking

Long running cron jobs can end up smashing over each other and creating a lot of havoc if not properly locked. There are two simple ways to keep that from happening -- one in bash and another useful program that is available by default on almost all Linux distributions.

## Using Bash

Placing this snippet at the beginning of any script will create a lockfile if one does not exist, populate it with a PID and exit if one exists and the PID contained is still running.

    LOCKFILE=/var/run/${0}.lock
    touch ${LOCKFILE}
    read LASTPID < ${LOCKFILE}
    [ ! -z "${LASTPID}" -a -d /proc/${LASTPID} ] && exit
    echo $$ > ${LOCKFILE}

# Using Flock

Flock lets you easily wrap any current program with locking so you don't even have to think about it. You like that don't you, you lazy asshole.

    /usr/bin/flock -n /var/run/myscript.lock /usr/local/bin/myscript
