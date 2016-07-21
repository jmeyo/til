# Getting The Device Behind A dm Object

Both LVM and dmcrypt use the device mapper to map devices to /dev/dm-N on the system. Errors in logs will often reference a /dev/dm-N that you'll need to map back to the actual device. Using `dmsetup ls` you can see a list of the devices and with `dmsetup /dev/dm-N` you can get the actual disk information you need to identify the drive.
