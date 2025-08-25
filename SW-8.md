<Mirpur-10-Huawei-SW>display current-configuration
!Software Version V200R005C10SPC800
!Last configuration was updated at 2025-08-09 17:31:05+00:00 by netxcore
!Last configuration was saved at 2025-08-09 17:34:16+00:00 by netxcore
#
sysname Mirpur-10-Huawei-SW
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
 hwtacacs server source-ip 172.16.183.234
 hwtacacs server shared-key cipher %^%#.BQ~E6-)b"iwgiSM2mRK]UF9'd~jR1F>cJGR,A|R%^%#
 hwtacacs server user-name domain-excluded
#
aaa
 default-domain admin huawei
 local-user netxcore password irreversible-cipher $1c$xnwfF&h&_T$_nBQVdI{BP,QVX"c"sK*r&.w#X+IJ8L^<8N&S+j4$
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
interface Vlanif3880
 description ***Agargaon-SW-Link***
 ip address 172.16.183.234 255.255.255.252
#
interface MEth0/0/0
#
interface Eth-Trunk2
 description ***Mirpur12-20G-Bundle***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 3000
 mode lacp-dynamic
#
interface Eth-Trunk3
 description ***REGO-DATA***
 port link-type trunk
 port trunk allow-pass vlan 1404 to 1408
 mode lacp-dynamic
#
interface 10GE1/0/1
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 101
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 8
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/2
 shutdown
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/3
 shutdown
 device transceiver 10GBASE-COPPER
#
interface 10GE1/0/4
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1483 1683 2483 3483
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 20
 device transceiver 10GBASE-COPPER
#
interface 10GE1/0/5
 description ***REGO***
 port link-type trunk
 port trunk allow-pass vlan 1392 to 1401
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/6
 description ***REGO***
 port link-type trunk
 port trunk allow-pass vlan 1392 to 1401
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/7
 description ***Mirpur12-SW-20G***
 eth-trunk 2
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/8
 description ***Mirpur12-SW-20G***
 eth-trunk 2
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/9
 shutdown
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/10
 shutdown
#
interface 10GE1/0/11
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 20 101
#
interface 10GE1/0/12
 description **REGO**
 port link-type trunk
 port trunk allow-pass vlan 1341 to 1343 1347 1349 1411 to 1413
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/13
#
interface 10GE1/0/14
#
interface 10GE1/0/15
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 8
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/16
#
interface 10GE1/0/17
#
interface 10GE1/0/18
#
interface 10GE1/0/19
#
interface 10GE1/0/20
 description ***DhakaColo-Panthapath***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/21
 description ***REGO-DATA**
 eth-trunk 3
 device transceiver 1000BASE-X
#
interface 10GE1/0/22
 description ***REGO-DATA**
 eth-trunk 3
 device transceiver 1000BASE-X
#
interface 10GE1/0/23
 shutdown
#
interface 10GE1/0/24
 shutdown
#
interface 40GE1/0/3
 description ***Agargaon-40G-SW***(port Exchange)
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 40GBASE-FIBER
#
interface 40GE1/0/4
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 40GE1/0/5
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 40GBASE-FIBER
#
interface 40GE1/0/6
 description ***Agargaon-SW***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 40GBASE-FIBER
#
interface 100GE1/0/1
 description ***Agargaon-SW***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 65535
 device transceiver 40GBASE-FIBER
#
interface 100GE1/0/2
 description ***Agargaon-SW-new***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 1
 device transceiver 40GBASE-FIBER
#
interface NULL0
#
ip route-static 0.0.0.0 0.0.0.0 172.16.183.233
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861BA010
snmp-agent community read cipher %^%#8I>JW#[w4IM&#wE@VZ(8wnI]:1Ol>1*+p-<>8JgV]w.6!"R*HBmd^/8CUtyHylYlQ,>MK6^2\aXfU@HO%^%#
snmp-agent community read cipher %^%#]'k=~c]Q(!2,E:HH24W&By0H*o=<|AL6~)8@^<aY]k\R%TL&cOZE<]2OT-qCDpDL-*L;c7m\nBR;ph{:%^%#
#
snmp-agent sys-info version all
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
dns resolve
dns server 8.8.4.4
dns domain ne
#
user-interface maximum-vty 15
#
user-interface con 0
 authentication-mode password
 set authentication password cipher $1c$j[e#6^S|mP$\#c3#9CsF@>GgnA-6=-0BpnI7jMSR,AO>L7)E:QU$
#
user-interface vty 0 4
 authentication-mode aaa
 user privilege level 3
#
user-interface vty 5 14
 authentication-mode password
 user privilege level 3
 set authentication password cipher $1c$(ccH;3Rs]0$OZ.18Fq|1K@7Z@4:)*-X2_zKNtVR-ZNO]BNH%0$H$
 protocol inbound telnet
#
return
<Mirpur-10-Huawei-SW>
