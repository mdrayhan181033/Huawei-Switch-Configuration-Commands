<MN-Huawei-SW>display current-configuration
!Software Version V200R005C10SPC800
!Last configuration was updated at 2025-08-19 15:17:42+00:00 by netxcore
!Last configuration was saved at 2025-08-19 15:17:45+00:00 by netxcore
#
sysname MN-Huawei-SW
#
port mode 100GE interface 40GE1/0/1 to 40GE1/0/2
#
device board 1 board-type CE6880-24S4Q2CQ-EI
#
drop-profile default
#
vlan batch 2 to 4094
vlan assign global 2 to 4094
#
telnet ipv6 server disable
#
hwtacacs enable
#
diffserv domain default
#
hwtacacs server template ht
 hwtacacs server authentication 172.20.1.206
 hwtacacs server authorization 172.20.1.206
 hwtacacs server accounting 172.20.1.206
 hwtacacs server source-ip 172.16.183.226
 hwtacacs server shared-key cipher %^%#dLgh.=>wU,o8r$+*>Y1Wq:3_H(d)"N{.MX3hm!L-%^%#
 hwtacacs server user-name domain-excluded
#
aaa
 user-name minimum-length 2
 default-domain admin huawei
 local-user netxcore password irreversible-cipher $1c$byn9T\#YlG$e\nySvPBu"Doi-W;$eHQ*piP(:YE+<dUdJD7AOcP$
 local-user netxcore service-type telnet
 local-user netxcore level 3
 local-user netxcore access-limit 10
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
interface Vlanif3880
 ip address 172.16.183.226 255.255.255.252
#
interface MEth0/0/0
#
interface Eth-Trunk3
 description ***Mirpur12-20G-Bundle***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 mode lacp-dynamic
#
interface Eth-Trunk4
 description ***D-net-Bundle**
 port link-type trunk
 undo port trunk allow-pass vlan 1
 port trunk allow-pass vlan 1050 1191 1385 1459 1697 1785 2212 2216 2385 2709
 port trunk allow-pass vlan 2750 2757 2870 to 2871 3385 3402
 stp root-protection
 stp bpdu-filter enable
 mode lacp-dynamic
#
interface Eth-Trunk5
#
interface Eth-Trunk6
 description ***Rego-Bundle-Speed**
 port link-type trunk
 port trunk allow-pass vlan 232 1342 to 1343 1399 1511 to 1515 1521 to 1525 2268 2322
 stp root-protection
 stp bpdu-filter enable
 mode lacp-dynamic
#
interface 10GE1/0/1
 description **Inspire-BroadBand-RDN**
 port link-type trunk
 port trunk allow-pass vlan 1249 1679 2644
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 15
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/2
 description ***Optimum-Communication***
 port link-type trunk
 undo port trunk allow-pass vlan 1
 port trunk allow-pass vlan 1277 to 1282
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 10
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/3
 description **SS-ONLINE-DATA**
 port link-type trunk
 port trunk allow-pass vlan 885 to 888
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 10
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/4
 description ***SS-ONLINE-DATA**
 port link-type trunk
 port trunk allow-pass vlan 700 to 703
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 10
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/5
 port link-type trunk
 undo port trunk allow-pass vlan 1
 port trunk allow-pass vlan 1085 1985 2085 3085
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/6
 description **REGO-DATA**
 port link-type trunk
 port trunk allow-pass vlan 20 1520 to 1525
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/7
 description ***Mirpur12-20G-Bundle***
 eth-trunk 3
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/8
 description ***Mirpur12-20G-Bundle***
 eth-trunk 3
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/9
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/10
 description ***MN-Client***
 port link-type trunk
 port trunk allow-pass vlan 291 1279 1439 1639 1988 2279 2439 2797 2871 3279
 port trunk allow-pass vlan 3439
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/11
 description **D-NET-GABTOLY**
 eth-trunk 4
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/12
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/13
 shutdown
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/14
 description ***SS-NETWORK-BKP***
 port link-type trunk
 port trunk allow-pass vlan 200 1264 1770 2109 2764 3108
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 8
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/15
 description ***JHONGKAR-IT***
 port link-type trunk
 port trunk allow-pass vlan 2695 2697 3116
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/16
 description ***Sweet-Online BKP***
 port link-type trunk
 port trunk allow-pass vlan 1315 1815 2315 3315
 stp root-protection
 port-security enable
 port-security maximum 10
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/17
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/18
 description ***D-net-BKP**
 eth-trunk 4
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/19
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/20
 shutdown
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/21
 shutdown
#
interface 10GE1/0/22
 port link-type trunk
 port trunk allow-pass vlan 1398 1798 2398 2662 3398
 device transceiver 1000BASE-X
#
interface 10GE1/0/23
 description ***Bangladesh-Internet-Service***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/24
 device transceiver 10GBASE-FIBER
#
interface 40GE1/0/3
 description ***Rego-Bundle-Speed***
 eth-trunk 6
 device transceiver 40GBASE-FIBER
#
interface 40GE1/0/4
 description ***Rego-Bundle-Speed***
 eth-trunk 6
 device transceiver 40GBASE-FIBER
#
interface 40GE1/0/5
 shutdown
#
interface 40GE1/0/6
 shutdown
#
interface 100GE1/0/1
 description ***Agargawn***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 1
 device transceiver 100GBASE-FIBER
#
interface 100GE1/0/2
 description ***Mohammodpur***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 100GBASE-FIBER
#
interface NULL0
#
ip route-static 0.0.0.0 0.0.0.0 172.16.183.225
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9920
snmp-agent community read cipher %^%#U)7\NHc]K@4H0@+:B[kM+6xB@M6oe#oW-f3Q~'}1\#<$#"7q{WV%qT3LSYf9#z/=0Qrm^A3WGfM52~7/%^%#
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
 set authentication password cipher $1c$+'Jw*r-@:@$2S'}HGbQlQj,#uW"1wi%h-_yFsuTgR&&|(E=NU(E$
#
user-interface vty 0 4
 authentication-mode aaa
 user privilege level 3
 protocol inbound telnet
#
user-interface vty 5 14
 authentication-mode password
 user privilege level 3
 set authentication password cipher $1c$0nPE)`YN"<$'"-nGw1%EJrV|!6Zc='4|IJc=$vkX50d(CF7fs!E$
 protocol inbound telnet
#
return
<MN-Huawei-SW>
