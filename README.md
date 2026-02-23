# ssh_on_a_Cisco_Switch
ssh on a layer-2 Cisco switch

Switch>enable
Switch#conf t

Enter configuration commands, one per line. End with CNTL/Z.
Switch (config) #hostname Switch1
Switch1(config)#username cisco password cis123
Switch1(config)#enable password cis123
Switch1(config)#service password-encryption
Switch1(config)#exit
Switch1#enable
Switch1#exit
Switch1>
password: ****
Switch1#conf t 
Switch1(config)#interface vlan 1
Switch1(config)#ip address 192.168.1.2 255.255.255.0
Switch1(config)#no shut
Switch1(config)#ip domain-name lab.local
Switch1(config)#crypto key generate rsa
1024 or above
Switch1(config)#ip ssh version 2
Switch1(config)#line vty 0 15
Switch1(config-line)#transport input ssh
Switch1(config-line)#login local
Switch1(config-line)#exit
Switch1(config)#no shutdown
Switch1(config)#exit
Switch1#write
Switch1#show ip ssh
Switch1#show running-config

