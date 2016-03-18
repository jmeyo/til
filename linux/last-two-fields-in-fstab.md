# Last Two Fields In fstab

The /etc/fstab file has all of the filesystems that need to be mounted on a Linux system. The final two fields are the dump and pass fields or fs_freq and fs_passno.

The dump field determines which filesystems need to be dumped. If this field isn't provided a 0 is assumed and the system assumes that the filesystem does not need to be dumped.

The pass field is used by fsck to determine the order in which to run checks after a reboot. The root filesystem should always be 1 and all other filesystems should be 2. If there is a 0 then the system assumes the filesystem does not need to be checked.
