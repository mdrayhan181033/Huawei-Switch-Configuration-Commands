<Agargaon-SW>     display current-configuration
!Software Version V200R021C00SPC600
#
sysname Agargaon-SW
#
vlan batch 2 to 4094
#
authentication-profile name default_authen_profile
authentication-profile name dot1x_authen_profile
authentication-profile name dot1xmac_authen_profile
authentication-profile name mac_authen_profile
authentication-profile name multi_authen_profile
authentication-profile name portal_authen_profile
#
domain huawei admin
#
telnet server enable
telnet server-source all-interface
telnet ipv6 server-source all-interface
#
http server-source -i MEth0/0/1
#
clock timezone 1 add 06:00:00
#
undo hwtacacs enable
#
diffserv domain default
#
radius-server template default
#
hwtacacs-server template ht
 hwtacacs-server authentication 172.20.1.206
 hwtacacs-server authorization 172.20.1.206
 hwtacacs-server accounting 172.20.1.206
 hwtacacs-server source-ip 172.16.183.210
 hwtacacs-server shared-key cipher %^%#Gx;WJQrR]Er0XCM(N>+)${/<:BWuiJ9/}r+@_t_J%^%#
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
 authentication-scheme 1-h
  authentication-mode hwtacacs local
 authentication-scheme default
  authentication-mode local
 authentication-scheme radius
  authentication-mode radius
 authorization-scheme default
  authorization-mode local
 authorization-scheme hwtacacs
  authorization-mode hwtacacs local
 accounting-scheme default
  accounting-mode none
 accounting-scheme hwtacacs
  accounting-mode hwtacacs
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
 domain huawei
  authentication-scheme 1-h
  accounting-scheme hwtacacs
  authorization-scheme hwtacacs
  radius-server default
  hwtacacs-server ht
 local-user noc password irreversible-cipher $1c$TIrA8;wz>&$S)4\'c8]@%ja:L("5*E/p-DcFy&<0'wo7E0EtxbD$
 local-user noc privilege level 3
 local-user noc service-type telnet ssh
 local-user netxcore password irreversible-cipher $1c$iO*cL7+R&8$U0ivAo$yo3CabMLwz=N39;mJOgiN1%C5>`~ng~j%$
 local-user netxcore privilege level 3
 local-user netxcore service-type telnet ssh
#
ntp-service ipv6 server disable
ntp-service unicast-server 10.11.1.26
#
interface Vlanif3880
 ip address 172.16.183.222 255.255.255.252
#
interface Vlanif3892
 ip address 172.16.183.210 255.255.255.252
#
interface MEth0/0/1
 ip address 192.168.1.253 255.255.255.0
#
interface Eth-Trunk1
 shutdown
#
interface Eth-Trunk2
 description ***Shewrapara-Bundle***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4093
 mode lacp
#
interface Eth-Trunk3
 shutdown
#
interface XGigabitEthernet0/0/1
 description *** BANGLADESH-ONLINE-BKP***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/2
 description **Inspire-Broadband**
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 1215 1276 1678 2637 2773
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 5
#
interface XGigabitEthernet0/0/3
 description ***REGO-DATA***
 port link-type trunk
 port trunk allow-pass vlan 1307 to 1312
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 15
#
interface XGigabitEthernet0/0/4
 undo negotiation auto
 description ***REGO-DATA***
 port link-type trunk
 port trunk allow-pass vlan 1456 to 1457
 port negotiation disable
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 15
#
interface XGigabitEthernet0/0/5
 description ***Voygar-Internet***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 508 1201 to 1205
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 7
#
interface XGigabitEthernet0/0/6
 shutdown
#
interface XGigabitEthernet0/0/7
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/8
 description ***Shewrapara-Link***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/9
 description description ***HOME-Touch-01-1036***
 port link-type trunk
 undo port trunk allow-pass vlan 1
 port trunk allow-pass vlan 1236 to 1240
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/10
 undo negotiation auto
 description description ***HOME-Touch-02-1009***
 port link-type trunk
 undo port trunk allow-pass vlan 1
 port trunk allow-pass vlan 1241 to 1245
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/11
 description MM-DOT-Net***
 port link-type trunk
 port trunk allow-pass vlan 1231 to 1235 1530
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/12
 description ***Super-UZ-Online***
#
interface XGigabitEthernet0/0/13
 shutdown
#
interface XGigabitEthernet0/0/14
 description ***NETX-Babu***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/15
 shutdown
#
interface XGigabitEthernet0/0/16
 shutdown
#
interface XGigabitEthernet0/0/17
 description ***Mridha-IT***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/18
 description ***Mridha-IT***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
 stp root-protection
 stp bpdu-filter enable
 port-security enable
 port-security max-mac-num 10
#
interface XGigabitEthernet0/0/19
 shutdown
#
interface XGigabitEthernet0/0/20
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface XGigabitEthernet0/0/21
 shutdown
#
interface XGigabitEthernet0/0/22
 shutdown
#
interface XGigabitEthernet0/0/23
 shutdown
#
interface XGigabitEthernet0/0/24
 shutdown
#
interface 100GE0/0/1
 shutdown
#
interface 100GE0/0/2
 description ***Firmgate-100G-SW***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/3
 description ***MN-POP***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4094
#
interface 100GE0/0/4
 description ***Mirpur-10-40G***
 port link-type trunk
 port trunk allow-pass vlan 2 to 4093
#
interface 100GE0/0/5
 description ***Free***
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4093
 stp instance 0 cost 1
#
interface 100GE0/0/6
 shutdown
 port link-type trunk
 port trunk allow-pass vlan 2 to 4093
#
interface NULL0
#
undo icmp name timestamp-request receive
#
ip route-static 0.0.0.0 0.0.0.0 172.16.183.209
#
snmp-agent
snmp-agent local-engineid 8000DDED033CC7861B9920
snmp-agent community read cipher %^%#'([;L^cl}2MQe2Y`*W*2BDdLOlhxN10bVqK@*<b'xV/O"N;Xq:(:Tz/(lt@!3'J"*]k(;-.+d|9jt3jU%^%#
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
ssh authorization-type default aaa
ssh server publickey rsa_sha2_512 rsa_sha2_256
#
user-interface con 0
 authentication-mode password
 set authentication password cipher $1c$wOwn.:uW.<$NnU&AkWN:Wr)uvDd%-W4;4fQKKItI>~,_vU3j]5-$
user-interface vty 0 2
 user privilege level 3
 idle-timeout 30 0
 protocol inbound telnet
user-interface vty 3 4
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
<Agargaon-SW>
