# Erase Master Boot Record

When PXE booting a lot of machines for provisioning you'll usually have PXE as your secondary boot option so post-provisioning the machine boots. An easy way to bring them back up on PXE boot is to clear the MBR with a simple dd.

`dd if=/dev/zero of=/dev/drive bs=512 count=1`
