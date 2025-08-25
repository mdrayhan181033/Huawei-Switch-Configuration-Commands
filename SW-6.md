<Firmgate-Huawei-SW>display current-configuration
!Software Version V200R005C10SPC800
!Last configuration was updated at 2025-08-25 01:00:53+00:00 by netxcore
!Last configuration was saved at 2025-08-09 17:35:17+00:00 by netxcore
#
sysname Firmgate-Huawei-SW
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
 hwtacacs server source-ip 172.16.183.230
 hwtacacs server shared-key cipher %^%#nl}UX74({U1U.vCDy/O75h=L+5*<RO7'Os+]'s_A%^%#
 hwtacacs server user-name domain-excluded
#
aaa
 default-domain admin huawei
 local-user radisson password irreversible-cipher $1c$R5|DP2qSS6$)k"_Kf:+27MXD4Xis.q>2sEV=[FLB'KNE8!(4,~.$
 local-user radisson service-type telnet
 local-user radisson level 3
 local-user radisson user-group manage-ug
 local-user netxcore password irreversible-cipher $1c$&S58'#teCD$jL's@+E'_=pcH2Y|M2TWkgF=-mO!e2Dpo:Aq1-L$$
 local-user netxcore service-type telnet
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
 ip address 172.16.183.230 255.255.255.252
#
interface MEth0/0/0
 ip address 10.10.100.2 255.255.255.0
#
interface Eth-Trunk1
 description **Agargaon-POP**
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp-static
#
interface Eth-Trunk2
 description ***Mohammadpur-POP***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/1
 description ***SW-Bond***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/2
 description **Agargaon-POP-1***
 shutdown
 eth-trunk 1
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/3
 description **Agargaon-POP-2***
 shutdown
 eth-trunk 1
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/4
 description **Agargaon-POP-3***
 shutdown
 eth-trunk 1
#
interface 10GE1/0/5
 description **Agargaon-POP-4***
 shutdown
 eth-trunk 1
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/6
 description ***Sumon-Vaia-Home***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 port-security enable
 port-security maximum 4
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/7
 description ***IT-Base-3rd-Link
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1206 1806 2206 2638 3206
 port-security enable
 port-security maximum 10
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/8
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/9
 description ***M.E.B-Technology***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1271 1794 2113 2746 3111
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 6
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/10
 description ***MKZ-FARMGATE-2***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 984 to 987
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security maximum 6
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/11
 description **Hishabe-bkp**
 port link-type trunk
 port trunk allow-pass vlan 423
 device transceiver 1000BASE-X
#
interface 10GE1/0/12
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 1000BASE-X
#
interface 10GE1/0/13
 description ******3-Online-BKP***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1040 1196 1841 1897 2040 2311 2701 3040 3311
 stp bpdu-filter disable
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/14
 description ***MKZ-Framgate***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/15
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 10GE1/0/16
 description ***BlueNet***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/17
 description ***Bluenet**
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 100 1725
 port-security enable
 port-security maximum 10
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/18
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/19
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 10GBASE-FIBER
#
interface 10GE1/0/20
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp loop-protection
 port-security enable
 port-security maximum 4
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
 device transceiver 10GBASE-FIBER
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
 description ***From-Agargoan-pop***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 40GBASE-FIBER
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
 description ***Khawaja-up-link***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp instance 0 cost 1
 device transceiver 100GBASE-FIBER
#
interface 100GE1/0/2
 description ***Agargaon-100G-SW***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 device transceiver 100GBASE-FIBER
#
interface NULL0
#
ip route-static 0.0.0.0 0.0.0.0 172.16.183.229
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9920
snmp-agent community read cipher %^%#TDQ}LVKC"JkhlW)9$4#"Oi0lB71q:JLXML,P8pkU.V$_;J/bs4Em]u&4fXT(D"VWL,3_B.f%,x&9U%4-%^%#
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
user-interface maximum-vty 15
#
user-interface con 0
 authentication-mode password
 set authentication password cipher $1c$[x\gU,fNj@$;$OoP>;Z@+t!:CB%;JW=.vg~CdPaH3_Y;|!"4rS6$
#
user-interface vty 0 4
 authentication-mode aaa
 user privilege level 3
 protocol inbound telnet
#
user-interface vty 5 14
 authentication-mode password
 user privilege level 3
 protocol inbound telnet
#
return
<Firmgate-Huawei-SW>
