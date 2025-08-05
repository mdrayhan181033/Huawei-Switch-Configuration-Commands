Lal-Mosjid-POP#show running-config
Building configuration...


Current configuration:
!
!version 2.2.0D build 97625
service timestamps log date
service timestamps debug date
service password-encryption
logging buffered 409400
!
hostname Lal-Mosjid-POP
!
!
!
!
!
spanning-tree mode mstp
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
aaa authentication login default group tacacs+ local
aaa authentication enable default none
aaa authorization commands 15 default group tacacs+
aaa authorization commands 0 default group tacacs+
aaa authorization exec default group tacacs+ local
aaa accounting commands 0 default start-stop group tacacs+
aaa accounting commands 15 default start-stop group tacacs+
aaa accounting network default start-stop group tacacs+
!
localauthor full
 exec privilege default 8
!
username netx password 7 0825042e57107f13226e
username noc author-group full password 7 082573797f3e3e44
!
!
!
!
!
!
interface Null0
!
interface GigaEthernet0/0
 no ip address
!
interface TGigaEthernet0/1
 description ***Bottolta-SW***
 spanning-tree cost 65535
 switchport mode trunk
!
interface TGigaEthernet0/2
 switchport trunk vlan-allowed 2-4094
 switchport mode trunk
!
interface TGigaEthernet0/3
 description ***Microlink-Data-L***
 switchport trunk vlan-allowed 2-4094
 switchport mode trunk
!
interface TGigaEthernet0/4
 switchport mode trunk
!
interface TGigaEthernet0/5
 shutdown
!
interface TGigaEthernet0/6
 description ***Media-Online***
 spanning-tree bpdufilter enable
 spanning-tree guard root
 switchport trunk vlan-allowed 1278,1495,1726,2214,2276,2614,3122,3214
 switchport mode trunk
 switchport port-security dynamic maximum 16
!
interface TGigaEthernet0/7
 shutdown
!
interface TGigaEthernet0/8
 description **Shapla-Net-Pri**
 switchport trunk vlan-allowed 1033,1121,1427,1927,2223,2713,3223
 switchport mode trunk
!
interface TGigaEthernet0/9
 shutdown
 switchport mode trunk
!
interface TGigaEthernet0/10
 description ***3G-Online-bkp***
 switchport mode trunk
!
interface TGigaEthernet0/11
 switchport trunk vlan-allowed 2-4094
 switchport mode trunk
!
interface TGigaEthernet0/12
 shutdown
!
interface TGigaEthernet0/13
 shutdown
 switchport mode trunk
!
interface TGigaEthernet0/14
 shutdown
!
interface TGigaEthernet0/15
 switchport mode trunk
!
interface TGigaEthernet0/16
 shutdown
 switchport mode trunk
!
interface TGigaEthernet0/17
 shutdown
 switchport mode trunk
!
interface TGigaEthernet0/18
 shutdown
!
interface TGigaEthernet0/19
 shutdown
!
interface TGigaEthernet0/20
 shutdown
!
interface TGigaEthernet0/21
 shutdown
!
interface TGigaEthernet0/22
 description ***JG-Online***
 switchport trunk vlan-allowed 1,1246,1953,2246,2775,3043
 switchport mode trunk
 no fiber-auto-config
 speed 1000
 duplex auto
!
interface TGigaEthernet0/23
 description ***Munna-Data***
 switchport trunk vlan-allowed 1,451,456-458,2503
 switchport mode trunk
 no fiber-auto-config
!
interface TGigaEthernet0/24
 switchport mode trunk
 no fiber-auto-config
 speed 1000
 duplex auto
!
interface CGigaEthernet0/1
 description ***Jurain-SW***
 spanning-tree cost 1
 switchport mode trunk
!
interface CGigaEthernet0/2
 description ***Microlink-Primary***
 spanning-tree bpdufilter enable
 spanning-tree guard root
 switchport trunk vlan-allowed 1,470,1341,1344,1555-1560,1787,1826,2270,2685
 switchport trunk vlan-allowed add 2686,3263
 switchport mode trunk
!
interface CGigaEthernet0/3
 shutdown
 switchport mode trunk
!
interface CGigaEthernet0/4
 description ***Fatullah-SW***
 switchport mode trunk
!
interface VLAN3100
 ip address 172.16.100.26 255.255.255.0
 no ip directed-broadcast
!
!
!
vlan 1-4094
!
!
!
!
!
!
!
!
!
!
!
!
!
!
ip route default 172.16.100.1
ip exf
!
ipv6 exf
!
!
!
!
!
ip http server
!
!
snmp-server community 0 Speed RO
!
radius-server host 192.168.254.11
radius-server key 7 0848481f51440213206e
!
tacacs-server host 172.20.1.206
tacacs-server key 7 0824112d543d7f13226e
!
line vty 0 6
 login authorization radius
!
!
time-zone tz 6 0
ntp server 183.177.72.201
!
!
!
!
!Pending configurations for absent linecards:
!
!No configurations pending global
Lal-Mosjid-POP#
