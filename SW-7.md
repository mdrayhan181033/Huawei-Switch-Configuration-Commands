<DhakaColo-Panthapath>display current-configuration
!Software Version V200R021C00SPC600
#
sysname DhakaColo-Panthapath
#
vlan batch 2 to 4094
#
stp instance 0 priority 0
#
authentication-profile name default_authen_profile
authentication-profile name dot1x_authen_profile
authentication-profile name dot1xmac_authen_profile
authentication-profile name mac_authen_profile
authentication-profile name multi_authen_profile
authentication-profile name portal_authen_profile
#
domain default_admin
#
telnet server enable
telnet server-source all-interface
#
http server-source -i MEth0/0/1
#
undo hwtacacs enable
#
diffserv domain default
#
radius-server template default
#
pki realm default
 certificate-check none
#
free-rule-template name default_free_rule
#
portal-access-profile name portal_access_profile
#
drop-profile default
#
aaa
 authentication-scheme default
  authentication-mode local
 authentication-scheme radius
  authentication-mode radius
 authorization-scheme default
  authorization-mode local
 accounting-scheme default
  accounting-mode none
 local-aaa-user password policy administrator
  password history record number 0
  password expire 0
 domain default
  authentication-scheme radius
  accounting-scheme default
  radius-server default
 domain default_admin
  authentication-scheme default
  accounting-scheme default
 local-user noc password irreversible-cipher $1c$It]Z*2g`"Z$[s>VX/w(r&Dp"bOa_]v.Y<r$J.tWb"Upal;]!KUH$
 local-user noc privilege level 3
 local-user noc service-type telnet ssh
 local-user huawei password irreversible-cipher $1c$Or"C@UW;AW$)@_v2o~z[8sTm:40ou\U9(53Uq4q7ZLd>y+lWkD*$
 local-user huawei privilege level 3
 local-user huawei service-type telnet ssh
 local-user netxcore password irreversible-cipher $1c$[Q`bDR*aqJ$R=%B*O!c!@u<81SAC\K)F#d.JP3272gMLE/9yKQ-$
 local-user netxcore privilege level 3
 local-user netxcore service-type telnet ssh
#
interface Vlanif1
#
interface Vlanif3985
 description ***MGT-VLAN***
 ip address 172.16.189.2 255.255.255.252
#
interface MEth0/0/1
 shutdown
#
e-trunk 2
 security-key simple 00E0FC0000000000
#
interface Eth-Trunk2
 description **MOTIJHEEL-POP**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk3
 description ***RS1-RTR-ae4***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk4
 description ***CR1-RTR***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk5
 description ***Dhaka-Colo-New-MX-204***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk6
 description ***SS-Online***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1052 1152 2045
 mode lacp
#
interface XGigabitEthernet0/0/1
 description **MIRPUR-10-UG-LINK**
 port link-type trunk
#
interface XGigabitEthernet0/0/2
 description ***NETX-Core-Super-MKT**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/3
 description ***MKT-2004***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/4
 shutdown
#
interface XGigabitEthernet0/0/5
 description ***DIS-02-xe-0/1/6***
 eth-trunk 5
#
interface XGigabitEthernet0/0/6
 shutdown
#
interface XGigabitEthernet0/0/7
 description ***DIS-02-xe-0/1/7***
 eth-trunk 5
#
interface XGigabitEthernet0/0/8
 description *****NEW-MX-204-***
 eth-trunk 5
#
interface XGigabitEthernet0/0/9
 description ***NEW-MX-204-XE-0/1/0***
 eth-trunk 5
#
interface XGigabitEthernet0/0/10
 description ***Dhaka-Colo-DIS-2-XE-0/1/1***
 eth-trunk 5
#
interface XGigabitEthernet0/0/11
 description **RTR-CR1**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/12
 description Exord Online
 port link-type trunk
 port trunk allow-pass vlan 1098
#
interface XGigabitEthernet0/0/13
 shutdown
#
interface XGigabitEthernet0/0/14
 shutdown
#
interface XGigabitEthernet0/0/15
 description ***Bijoy-Online***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 500 1849 2336
#
interface XGigabitEthernet0/0/16
 description *AKAMAI-MIKROTIK*
 port link-type trunk
 port trunk allow-pass vlan 1901 to 1905
#
interface XGigabitEthernet0/0/17
 description ***RS1-RTR-ae4***
 shutdown
 eth-trunk 3
#
interface XGigabitEthernet0/0/18
 description **SK-TRADERS**
 port link-type trunk
 port trunk allow-pass vlan 306 to 309 312 2147 3012
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/19
 description ***CR1-RTR***
 eth-trunk 4
#
interface XGigabitEthernet0/0/20
 description ***CR1-RTR***
 eth-trunk 4
#
interface XGigabitEthernet0/0/21
 description ***SS-Online***
 shutdown
 eth-trunk 6
#
interface XGigabitEthernet0/0/22
 description ***SS-Online***
 shutdown
 eth-trunk 6
#
interface XGigabitEthernet0/0/23
 shutdown
#
interface XGigabitEthernet0/0/24
 description **BSCCL-COLOCITY**
 shutdown
 port link-type access
 port default vlan 854
#
interface XGigabitEthernet0/0/25
 description ***RS1-RTR-ae4***
 shutdown
 eth-trunk 3
#
interface XGigabitEthernet0/0/26
 description ***RS1-RTR-ae4***
 shutdown
 eth-trunk 3
#
interface XGigabitEthernet0/0/27
 description **3-Online**
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1040 1196 1841 1897 2040 2311 3040 3311
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/28
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/29
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/30
 description **Panthopath-pop-UG-link**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/31
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/32
 description BSCCL-PRIMARY
 port link-type trunk
 port trunk allow-pass vlan 1150 1152
#
interface XGigabitEthernet0/0/33
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/34
 description **MOTIJHEEL-POP**
 eth-trunk 2
#
interface XGigabitEthernet0/0/35
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/36
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/37
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/38
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/39
 description ***DIS-02-XE-0/1/7***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/40
 description ***DIS-01-XE-0/1/1***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/41
 description **MX204-NRB**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/42
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/43
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/44
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/45
 shutdown
#
interface XGigabitEthernet0/0/46
 shutdown
#
interface XGigabitEthernet0/0/47
 shutdown
#
interface XGigabitEthernet0/0/48
 description **Ericsson-Server**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 30
#
interface 100GE0/0/1
 description ***Panthapath-Pop***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/2
 description ***Firmgate-Link***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/3
 description ***FNA-SW***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/4
 description **Dhakacolo-MX-204**
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/5
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/6
 description ***PTX-KHAWAJA-RT***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface NULL0
#
undo icmp name timestamp-request receive
#
ip route-static 0.0.0.0 0.0.0.0 172.16.189.1
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9920
snmp-agent community read cipher %^%##&$NAA.~zSy-(R+$_eQV1,=I;n2gA3Sv$fYIhWq/23Q8J|g!3#!Fz-5*r*91'QAjKeMsD9""Hb+@(J:=%^%#
snmp-agent sys-info version v2c v3
snmp-agent protocol source-status all-interface
snmp-agent protocol source-status ipv6 all-interface
#
stelnet server enable
ssh server cipher aes256_ctr aes128_ctr
ssh server hmac sha2_256
ssh server key-exchange dh_group16_sha512 dh_group15_sha512 dh_group14_sha256 dh_group_exchange_sha256
ssh client cipher aes256_ctr aes128_ctr
ssh client hmac sha2_256
ssh client key-exchange dh_group16_sha512 dh_group15_sha512 dh_group14_sha256 dh_group_exchange_sha256
ssh server dh-exchange min-len 2048
ssh server publickey rsa_sha2_512 rsa_sha2_256
#
user-interface con 0
 authentication-mode password
 set authentication password cipher $1c$.`b5U!U;1Y$JDAR1BDDH6eqJQ,\MGt%FyI}A5YH\A/_U#Cm5q7J$
user-interface vty 0 4
 authentication-mode aaa
 user privilege level 3
 protocol inbound telnet
user-interface vty 16 20
 authentication-mode aaa
 user privilege level 3
 protocol inbound telnet
#
dot1x-access-profile name dot1x_access_profile
#
mac-access-profile name mac_access_profile
#
ops
#
return
<DhakaColo-Panthapath>
