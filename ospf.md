## Конфигурация OSPF
Конфигурация OSPF для Core1+RSRVCore1
~~~
conf t
router ospf 10
router-id 1.1.1.1
network 192.168.1.96 0.0.0.31 area 0
network 192.168.2.0 0.0.0.7 area 0
network 192.168.1.32 0.0.0.15 area 0
network 192.168.1.48 0.0.0.63 area 1 
network 192.168.1.0 0.0.0.31 area 1
~~~
Конфигурация OSPF для Core2+RSRVCore2
~~~
conf t
router ospf 10
router-id 2.2.2.2
network 192.168.2.0 0.0.0.7 area 0
network 192.168.1.96 0.0.0.31 area 0
network 192.168.0.128 0.0.0.127 area 2
network 192.168.0.0 0.0.0.127 area 3
~~~

Конфигурация OSPF для DIST1
~~~
conf t
router ospf 10
 router-id 3.3.3.3
 network 192.168.1.48 0.0.0.63 area 1
 network 192.168.1.96 0.0.0.31 area 0
exit
~~~

Конфигурация OSPF для DIST2
~~~
conf t
router ospf 10
 router-id 4.4.4.4
 network 192.168.1.0 0.0.0.31 area 1
 network 192.168.1.96 0.0.0.31 area 0
exit
~~~
Конфигурация OSPF для DIST4
~~~
conf t
router ospf 10
 router-id 5.5.5.5
 network 192.168.0.128 0.0.0.127 area 2
 network 192.168.1.96 0.0.0.31 area 0
exit
~~~

Конфигурация OSPF для DIST5
~~~
conf t
router ospf 10
 router-id 6.6.6.6
 network 192.168.0.0 0.0.0.127 area 3
 network 192.168.1.96 0.0.0.31 area 0
exit
~~~
