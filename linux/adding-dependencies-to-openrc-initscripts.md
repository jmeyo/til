# Adding Dependencies to OpenRC Initscripts

In complex setups you'll often find yourself having to add dependencies to initscripts so they depend on specific network devices or other daemons to start up first. Unfortunately, when you upgrade your setup your changes to the initscripts themselves can be eliminated. In addition to that there is a "proper" way to go about appending dependencies to initscripts use the /etc/conf.d file.

## Negating a dependency in a conf.d file for an initscript:
`rc_need="!net"`

## Making sure a dependency starts before another:
`rc_before="lvm"`

## Making sure a dependency starts after another:
`rc_after="dmcrypt"`

## Making sure a dependency provides for a requirement:
`rc_provides="net"`

## Making sure a dependency uses a requirement:
`rc_use="net"`

## Just adding to the /etc/rc.conf
`rc_service_name_need="!net"`

[Reference: Gentoo OpenRC Documentation](https://wiki.gentoo.org/wiki/OpenRC#Dependency_behavior(
