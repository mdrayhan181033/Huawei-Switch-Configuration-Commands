
<Bongo-Bazar-SW>display current-configuration
!Software Version V200R005C10SPC800
!Last configuration was updated at 2025-07-30 22:48:39+00:00 by netxcore
!Last configuration was saved at 2025-07-30 17:39:30+00:00 by netxcore
#
sysname Bongo-Bazar-SW
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
dot1x enable
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
 hwtacacs server source-ip 172.16.185.94
 hwtacacs server shared-key cipher %^%##F#2LP}UWDh9o<2ViC\&4[iHT#V/[.pv-}+P[3E+%^%#
 hwtacacs server user-name domain-excluded
#
aaa
 default-domain admin huawei
 local-user radisson password irreversible-cipher $1c$R<V0Qyhvq"$8bi-%s{2),_y-l+MRAG7D\7nSbZ)0~QBTM+FTQ!3$
 local-user radisson service-type telnet ssh
 local-user radisson level 3
 local-user radisson user-group manage-ug
 local-user netxcore password irreversible-cipher $1c$R_C<G^Y8F$$19@XRi~LKPpIX*.KSul21+P5H)%D>E~7'9U=`o!3$
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
interface Vlanif3989
 ip address 172.35.0.22 255.255.255.252
#
interface MEth0/0/0
#
interface 10GE1/0/1
 description **Bridge-MKT**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/2
 description **cloud-business**
 port link-type trunk
 port trunk allow-pass vlan 1020 1040 1820 1841 2022 2040 2763 2775 3020 3040
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/3
 description *** Palton Local New ***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/4
 description ***STL-Gulisthan-from-Khawja***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/5
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/6
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/7
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 1000BASE-X
#
interface 10GE1/0/8
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/9
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/10
 description ***Bongobazar-Wasim-Bhai***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4092
 device transceiver 10GBASE-COPPER
#
interface 10GE1/0/11
 description ***Bongobazar-Wasim-Bhai***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-COPPER
#
interface 10GE1/0/12
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-COPPER
#
interface 10GE1/0/13
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/14
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/15
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/16
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/17
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/18
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/19
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/20
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/21
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/22
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/23
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/24
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 40GE1/0/3
 shutdown
#
interface 40GE1/0/4
 shutdown
#
interface 40GE1/0/5
 shutdown
#
interface 40GE1/0/6
 shutdown
 device transceiver 40GBASE-FIBER
#
interface 100GE1/0/1
 description **Kazla-Uplink**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 100GBASE-FIBER
#
interface 100GE1/0/2
 description **Panthapath-SW**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 100GBASE-FIBER
#
interface NULL0
#
ip route-static 0.0.0.0 0.0.0.0 172.35.0.21
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9920
snmp-agent community read cipher %^%#6.XVO_5e/5~JKQ9s\2^:gGae1Z%|S1Dg%7@K<jY256y#Vy;)>FI06]!4w!P-*VG:5H<>EP<|"wP5q|V)%^%#
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
 set authentication password cipher $1c$'D9O+]aw2C$2~E|%f0!IVndmyD2-(e0^[K$+&>TIE/>82JrdOD=$
#
user-interface vty 0 4
 authentication-mode aaa
 user privilege level 3
#
user-interface vty 5 14
 authentication-mode password
 user privilege level 3
 set authentication password cipher $1c$cdrdMW&U@5$tINsG\Ojv&FEd)NMc#9:+O=f0Awlb:M80sYHGkfU$
 protocol inbound telnet
#
return
<Bongo-Bazar-SW>
