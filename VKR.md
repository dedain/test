## Конфигурация стекирования Центральный Офис
**На CORE1**
~~~
en
conf t
stackwise-virtual
domian 100
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
