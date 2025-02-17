## Конфигурация стекирования Центральный Офис
**На CORE1**
~~~
en
conf t
stackwise-virtual
domian 100
priority 15
int range gi0/3-4
stackwise-virtual link1
ex
int gi0/14
stackwise-virtual dual-active-detection
ex
do wr
ex
reload
~~~
**На RSRVCORE1**
~~~
en
conf t
stackwise-virtual
domian 100
priority 10
int range gi0/3-4
stackwise-virtual link1
ex
int gi0/14
stackwise-virtual dual-active-detection
ex
do wr
ex
reload
~~~


## Конфигурация стекирования Офис Продаж
**На CORE2**
~~~
en
conf t
stackwise-virtual
domian 200
priority 15
int range gi0/3-4
stackwise-virtual link1
ex
int gi0/12
stackwise-virtual dual-active-detection
ex
do wr
ex
reload
~~~
**На RSRVCORE2**
~~~
en
conf t
stackwise-virtual
domian 200
priority 10
int range gi0/3-4
stackwise-virtual link1
ex
int gi0/12
stackwise-virtual dual-active-detection
ex
do wr
ex
reload
~~~
### После выполнения перечисленных команд l3 коммутаторы объеденины в стеки, дальнейшая настройка может проводиться на любом из коммутатров, распространяться будет на весь стек

## Конфигурация стекирования Центральный Офис
~~~
int Port-channel1
  no switchport
  ip address 203.0.113.4 255.255.255.252
  ex
int range gi0/1-2
  channel-group 1 mode active
  ex
~~~
~~~
int Port-channel2
  no switchport
  ip address 192.168.1.103 255.255.255.224
  ex
int range gi0/5-6, gi0/11
  channel-group 2 mode active
  ex
~~~
~~~
int Port-channel3
  no switchport
  ip address 192.168.1.104 255.255.255.224
  ex
int range gi0/7-8, gi0/12
  channel-group 3 mode active
  ex
~~~
~~~
int Port-channel4
  no switchport
  ip address 192.168.1.105 255.255.255.224
  ex
int range gi0/9-10, gi0/13
  channel-group 4 mode active
  ex
~~~
