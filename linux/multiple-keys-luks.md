# Multiple Keys On A LUKS Device

Encrypted LUKS devices can have up to 8 keys for a single device. This lets you do a number of fancy things like:

- rolling encryption keys
- individual keys for each machine then a master backup key
- key swapping with a way to test that your new key works

## Adding A LUKS Key to A Device

`cryptsetup luksAddKey ${device} ${new_key} -d ${old_key}`

## Dump LUKS Device Information (Including Key Slots)

`cryptsetup luksDump ${device}`
