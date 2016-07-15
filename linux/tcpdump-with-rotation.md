# Using tcpdump with Automatic Rotation

The tcpdump command is extremely useful and pairs well with tools like Wireshark for quickly viewing and parsing captures. What I didn't know is that it could be configured to automatically dump traffic at a given interval in seconds (-G) as well as keep only a certain number of those files (-W).

`tcpdump -G 900 -w '%Y-%m-%d_%H:%M:%S.pcap' -W 96`

That command will rotate every 15 minues and keep only 96 15 minute chunks at a time.
