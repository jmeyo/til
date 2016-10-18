# pscap -- See Process Capabilities

The pscap tool can be used to show what capabilities processes on your system possess. This can be very useful for security auditing -- particularly in containerization cases like Docker.

## Sample Output
    pscap
    ppid  pid   name        command           capabilities
    1     289   root        systemd-journal   chown, dac_override, dac_read_search, fowner, setgid, setuid, sys_ptrace, sys_admin, audit_control, mac_override, syslog, audit_read
    1     399   root        systemd-udevd     full
    1     510   root        lvmetad           full
    1     528   systemd-timesync  systemd-timesyn   sys_time
    1     636   root        bitlbee           full
    1     637   root        systemd-logind    chown, dac_override, dac_read_search, fowner, kill, sys_admin, sys_tty_config, audit_control, mac_admin
    1     673   root        NetworkManager    dac_override, kill, setgid, setuid, net_bind_service, net_admin, net_raw, sys_module, sys_chroot, audit_write
    1     692   root        dockerd           full
    1     699   root        cupsd             full
    1     707   root        login             full
    692   724   root        docker-containe   full
    1     768   root        cups-browsed      full
    1     798   root        wpa_supplicant    full
    1216  1218  root        xf86-video-inte   full
    1003  1330  piffey      gnome-keyring-d   ipc_lock +
    673   1726  root        dhclient          dac_override, kill, setgid, setuid, net_bind_service, net_admin, net_raw, sys_module, sys_chroot, audit_write
    1     1926  root        upowerd           full

## Capabilities

You can run `man capabilities` to find the definition of any capabilities.



Inspiration for this post is from a RedHat article titled [Secure Your Containers With This One Weird Trick](http://rhelblog.redhat.com/2016/10/17/secure-your-containers-with-this-one-weird-trick/). Most shocking is that RedHat is resulting to shitty clickbait headlines.
