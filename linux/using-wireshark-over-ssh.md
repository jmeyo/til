# Using Wireshark Over SSH

Wireshark provides a number of hand-holding filters for analyzing large amounts of traffic. You can dump raw tcpdump through SSH and pipe it into Wireshark for analysis, then save the resulting capture for later.

`ssh user@host tcpdump -U -s0 -w - 'not port 22' | wireshark-gtk -k -i -`
