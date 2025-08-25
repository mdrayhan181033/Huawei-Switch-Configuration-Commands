<Basabo-SW>display current-configuration
!Software Version V200R021C00SPC600
#
sysname Basabo-SW
#
vlan batch 2 to 4094
#
stp mode rstp
stp instance 0 priority 0
#
authentication-profile name default_authen_profile
authentication-profile name dot1x_authen_profile
authentication-profile name dot1xmac_authen_profile
authentication-profile name mac_authen_profile
authentication-profile name multi_authen_profile
authentication-profile name portal_authen_profile
#
undo ntdp enable
#
telnet server enable
telnet server-source all-interface
#
http server-source -i MEth0/0/1
#
clock timezone BDT add 06:00:00
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
 local-user noc password irreversible-cipher $1c$)4<uBc;"rV$:oA/5R$c6X+-4"OH"1q@%_@P#4Mi"SJ1Ic8ZRx#I$
 local-user noc privilege level 3
 local-user noc service-type telnet ssh
 local-user netxcore password irreversible-cipher $1c$^pz3Au[waM$r=1$JxaUq@gL]^XN;sm"FI|;GDp6:EPCfoF-]tWC$
 local-user netxcore privilege level 3
 local-user netxcore service-type telnet ssh
#
ntp-service unicast-peer 10.11.1.26
#
interface Vlanif1
#
interface Vlanif3987
 ip address 172.16.189.54 255.255.255.252
#
interface MEth0/0/1
 shutdown
#
interface Eth-Trunk1
 description ***Kazla-Bundle***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk2
 description ***Khawja-Bundle***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk3
 shutdown
#
interface Eth-Trunk4
 shutdown
#
interface Eth-Trunk5
 shutdown
#
interface Eth-Trunk6
 shutdown
#
interface Eth-Trunk7
 description ***Bundle-with-GGC-Node***
 port link-type access
 port default vlan 108
 mode lacp
#
interface Eth-Trunk8
 shutdown
#
interface Eth-Trunk9
 shutdown
#
interface Eth-Trunk10
 shutdown
#
interface Eth-Trunk11
 description ***Bundle-with-NTTN-Juniper***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface Eth-Trunk12
 description ***Bundle-with-60g-GGC***
 port link-type access
 port default vlan 20
 mode lacp
#
interface Eth-Trunk13
 description ***Bundle-with-60g-GGC***
 port link-type access
 port default vlan 20
 mode lacp
#
interface Eth-Trunk14
 description ***Bundle-with-60g-GGC***
 port link-type access
 port default vlan 20
 mode lacp
#
interface Eth-Trunk15
 description ***FNA-GGC-SW-Bundle***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 mode lacp
#
interface XGigabitEthernet0/0/1
#
interface XGigabitEthernet0/0/2
 description ***FLASH-NET***
 port link-type trunk
 port trunk allow-pass vlan 1470 1670 2470 2771 3470
#
interface XGigabitEthernet0/0/3
#
interface XGigabitEthernet0/0/4
#
interface XGigabitEthernet0/0/5
#
interface XGigabitEthernet0/0/6
#
interface XGigabitEthernet0/0/7
#
interface XGigabitEthernet0/0/8
 description ***Aftabnagor-LINK***
 port link-type trunk
 port trunk allow-pass vlan 100 150 320 712 1022 1033 1037 1039 1069 1081
 port trunk allow-pass vlan 1097 to 1098 1108 1121 1137 1185 1191 1195 1207 1211 to 1215 1218
 port trunk allow-pass vlan 1221 1230 1247 1251 1265 1271 1273 1285 1297 to 1298 1314
 port trunk allow-pass vlan 1320 1344 1360 1378 1404 1414 1437 1469 1489 1620
 port trunk allow-pass vlan 1626 1634 1637 1641 1668 to 1669 1689 1701 1720 1729 1744
 port trunk allow-pass vlan 1759 to 1761 1764 1778 1781 1788 to 1789 1803 1807 1822 to 1823 1849 1872
 port trunk allow-pass vlan 1904 1924 1933 1937 1946 1954 1974 2033 2039 2048
 port trunk allow-pass vlan 2077 2081 2098 2110 2123 2129 2135 2137 to 2138 2162 2164
 port trunk allow-pass vlan 2185 2189 2195 2207 2218 2230 2239 2247 2271 2273
 port trunk allow-pass vlan 2323 2326 2339 2360 2378 2421 2437 2469 2489 2601
 port trunk allow-pass vlan 2630 2632 to 2633 2641 2643 2669 2678 2682 2684 2751 2759 to 2760
 port trunk allow-pass vlan 2763 2765 3003 3005 3030 3033 3069 3081 3093 to 3094 3122
 port trunk allow-pass vlan 3135 3137 3144 to 3146 3160 3181 3185 3195 3200 3207 3209
 port trunk allow-pass vlan 3218 3230 3247 3271 3273 3339 3360 3378 3403 3457
 port trunk allow-pass vlan 3469 3489 3887 to 3888 3904 3930
#
interface XGigabitEthernet0/0/9
#
interface XGigabitEthernet0/0/10
#
interface XGigabitEthernet0/0/11
#
interface XGigabitEthernet0/0/12
#
interface XGigabitEthernet0/0/13
 shutdown
#
interface XGigabitEthernet0/0/14
#
interface XGigabitEthernet0/0/15
#
interface XGigabitEthernet0/0/16
#
interface XGigabitEthernet0/0/17
 shutdown
#
interface XGigabitEthernet0/0/18
 description ***Net-Link***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/19
#
interface XGigabitEthernet0/0/20
#
interface XGigabitEthernet0/0/21
#
interface XGigabitEthernet0/0/22
 description ***Anas-Online***
 port link-type trunk
 port trunk allow-pass vlan 1061 1837 1883 2061 2703 3061
#
interface XGigabitEthernet0/0/23
#
interface XGigabitEthernet0/0/24
#
interface 100GE0/0/1
#
interface 100GE0/0/2
 description ***Basabo-kazla***
 eth-trunk 1
#
interface 100GE0/0/3
 description ***Basabo-kazla***
 eth-trunk 1
#
interface 100GE0/0/4
 description ***Basabo-to-Khawja***
 eth-trunk 2
#
interface 100GE0/0/5
 description ***Basabo-to-Khawja***
 eth-trunk 2
#
interface 100GE0/0/6
 shutdown
#
interface NULL0
#
undo icmp name timestamp-request receive
#
ip route-static 0.0.0.0 0.0.0.0 172.16.189.53
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9800
snmp-agent community read cipher %^%#N{7_<\5o]CKRI35lI-c(ZE{G<wWW|P}9y(NF,NVY{a}M1zm1OVJ`qkQ28Yv~ILzXUNg#p~_OD+Kyd096%^%#
snmp-agent sys-info version all
snmp-agent protocol source-status all-interface
undo snmp-agent protocol source-status ipv6 all-interface
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
 set authentication password cipher $1c$8kJ7XRZ)AL$p54;N{uRK'(_jcPdiF$N7CzSD0H3{C5G+|$bF~|%$
user-interface vty 0 4
 authentication-mode aaa
 protocol inbound telnet
user-interface vty 16 20
#
dot1x-access-profile name dot1x_access_profile
#
mac-access-profile name mac_access_profile
#
ops
#
return
<Basabo-SW>
