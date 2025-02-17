## Конфигурация стекирования
**На CORE1**
~~~
en
conf t
stackwise-virtual
domian 100
int range gi0/3-4
stackwise-virtual link1
ex

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

~~~
