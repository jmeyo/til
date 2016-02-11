# World Wide Identifiers

World Wide Identifiers (WWID) -- sometimes called World Wide Names (WWN) -- are unique identifiers used in storage technology. Linux uses WWNs -- along with serial numbers -- to provide symbolic links to the real device entries in the /dev directory. [Organizational Unique Identifiers](http://standards.ieee.org/regauth/oui/oui.txt) (OUIs) are tied to certain WWNs. You can use this to identify disk manufactururers in addition to the serial number symbolic links provided in the /dev/disk/by-id directory.

Some common OUIs tied to WWNs include:
* 00:14:EE - Western Digital
* 00:0C:50 - Seagate Technology

This can be especially useful when scripting the provisioning of large storage arrays.
