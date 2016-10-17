# Recovering LUKS Keys From Mounted Volumes

Ever accidentally overwritten or deleted that master key for a LUKS volume? If it's mounted, not a problem!

1. Confirm you can extract the old master key.
   `dmsetup table ${MAPPER} --showkeys`
2. Create a new keyfile.
   `dd if=/dev/urandom of=${NEW_KEYFILE} bs=128 count=1`
3. Convert the old key to binary and use it to add a new key.
   `cryptsetup luksAddKey ${DEVICE} ${NEW_KEYFILE} --master-key-file <(dmsetup table --showkey ${MAPPER} | awk '{print $5}' | xxd -r -p)`
4. Confirm your new key is enabled.
   `cryptsetup luksDump ${DEVICE} | grep ENABLED`

You can now confirm your ability to decrypt the device with a luksClose and luksOpen before rebooting confidently.
