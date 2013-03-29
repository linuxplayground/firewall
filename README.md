firewall
========

A small repo of the firewall rules on my new openSuSE install.

This script does the following things:
* Stop the system firewall altogether
* Reset any previously existing customizations to create a clean slate
* Set default policies to allow outbound and block all inbound and forward traffic
* Allow loopback traffic
* Allow any traffic that is related or established using the conntrack module.  This is reply traffic.
* Allow port 22 for SSH
* Allow traffic to and from the internal vboxnet0 (host only network defined by Oracle Virtual Box)
* Masquerade all traffic on the subnet defined by vboxnet0
* Drop all other input traffic.  (Possibly redundant based on policy defined at the beginning)
* Ensure that the dnsmasq service is running so that vboxnet0 hosts will be able to get an ip address.
* Ensure that ip\_forwarding\_ is turned on.

The config file for dnsmasq is also included.
