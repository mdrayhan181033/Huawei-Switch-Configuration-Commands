<Mohammadpur-Huawei-SW> display current-configuration
!Software Version V200R005C10SPC800
!Last configuration was updated at 2025-07-07 21:03:32+06:00 by netxcore
!Last configuration was saved at 2025-07-07 21:03:42+06:00 by netxcore
#
clock timezone BD add 06:00:00
#
sysname Mohammadpur-Huawei-SW
#
port mode 100GE interface 40GE1/0/1 to 40GE1/0/2
#
device board 1 board-type CE6880-24S4Q2CQ-EI
#
drop-profile default
#
ntp server disable
ntp unicast-server 10.11.1.26
#
vlan batch 2 to 4094
vlan assign global 2 to 4094
#
dot1x enable
#
telnet ipv6 server disable
#
radius enable
#
hwtacacs enable
#
diffserv domain default
#
hwtacacs server template ht
 hwtacacs server authentication 172.20.1.206
 hwtacacs server authorization 172.20.1.206
 hwtacacs server accounting 172.20.1.206
 hwtacacs server source-ip 172.16.183.218
 hwtacacs server shared-key cipher %^%#{(J&.0d>"5dZ)6:oSROTSTVJ3`jMH,*|f+Vl^*)~%^%#
 hwtacacs server user-name domain-excluded
#
aaa
 default-domain admin huawei
 local-user admin password irreversible-cipher $1c$4mGm6H6Z,9$~bKU6=}(\-!^zK2vhqD!35\E%pW+#YdzbT66<*\E$
 local-user admin service-type telnet ssh
 local-user admin level 3
 local-user admin user-group manage-ug
 local-user netxcore password irreversible-cipher $1c$78)INi{go<$'`+3Lo8$j~'3[!=s_(l1UWSoR&|[`$CP-XRnTXU=$
 local-user netxcore service-type telnet ssh
 local-user netxcore level 3
 local-user netxcore user-group manage-ug
 #
 authentication-scheme default
 #
 authentication-scheme 1-h
  authentication-mode hwtacacs local
 #
 authorization-scheme default
 #
 authorization-scheme hwtacacs
  authorization-mode hwtacacs local
 #
 accounting-scheme default
 #
 accounting-scheme hwtacacs
  accounting-mode hwtacacs
 #
 domain default
 #
 domain default_admin
 #
 domain huawei
  authentication-scheme 1-h
  authorization-scheme hwtacacs
  accounting-scheme hwtacacs
  hwtacacs server ht
  service-type terminal telnet ssh dot1x
#
stack
#
license
#
interface Vlanif3892
 ip address 172.16.183.218 255.255.255.252
#
interface MEth0/0/0
 ip address 10.10.150.2 255.255.255.252
#
interface 10GE1/0/1
 shutdown
#
interface 10GE1/0/2
 description ***Razzak-Data***
 port link-type trunk
 port trunk allow-pass vlan 345 to 348
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/3
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1300 to 1301 2310 2707 3390
 device transceiver 10GBASE-FIBER
 speed 1000
#
interface 10GE1/0/4
 description **Shewrapara-Link**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/5
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1032 1632 2032 3132
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/6
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/7
 description Grammen-Net
 port link-type trunk
 port trunk allow-pass vlan 1032 1632 2032 3132
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/8
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/9
 shutdown
#
interface 10GE1/0/10
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/11
 shutdown
#
interface 10GE1/0/12
#
interface 10GE1/0/13
 shutdown
#
interface 10GE1/0/14
 description **SK-Traders**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 6
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/15
 shutdown
#
interface 10GE1/0/16
 shutdown
#
interface 10GE1/0/17
 shutdown
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/18
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/19
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/20
 shutdown
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/21
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/22
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/23
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/24
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 40GE1/0/3
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 40GE1/0/4
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 40GE1/0/5
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 40GE1/0/6
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE1/0/1
 description ***Adnan-SW-Link***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 1
 device transceiver 100GBASE-FIBER
#
interface 100GE1/0/2
 description ***MN-POP-Link***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 30000
 device transceiver 100GBASE-FIBER
#
interface NULL0
#
ip route-static 0.0.0.0 0.0.0.0 10.10.150.1
ip route-static 0.0.0.0 0.0.0.0 172.16.183.217
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9920
snmp-agent community read cipher %^%#_a=-.!Dk17Y]ggREl~R'i^%.B@SL;AfQp48XR\_ACCX.5ruN~$7c(>S3oN$(vF'[7n+x,R`*=R7!ovFG%^%#
#
snmp-agent sys-info version v2c v3
#
stelnet server enable
ssh authorization-type default aaa
#
ssh server cipher aes256_ctr aes128_ctr
ssh server hmac sha2_256_96 sha2_256 sha1_96
ssh server key-exchange dh_group_exchange_sha256 dh_group_exchange_sha1 ecdh_sha2_nistp256 ecdh_sha2_nistp384 ecdh_sha2_nistp521 sm2_kep
#
ssh server dh-exchange min-len 2048
#
ssh client cipher aes256_gcm aes128_gcm aes256_ctr aes192_ctr aes128_ctr aes256_cbc aes128_cbc 3des_cbc
#
user-interface maximum-vty 15
#
user-interface con 0
 authentication-mode password
 set authentication password cipher $1c$K\{oXfg]=R$`I+<I`J/f!a9-u7+2(o2A"A-DA:v`UPzdkWx%!dS$
#
user-interface vty 0 4
 authentication-mode aaa
 user privilege level 3
#
user-interface vty 5 14
 authentication-mode password
 user privilege level 3
 set authentication password cipher $1c$04HO0ZssVG$0;a-SD}i=8ev8f!E_z}YPOv;~:V}3)r\v5R#!b+/$
 protocol inbound telnet
#
return
<Mohammadpur-Huawei-SW>
