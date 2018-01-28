# ConfigService

* issue#1:
client无法获取service中dev配置文件的form.
https://segmentfault.com/q/1010000007939615/a-1020000008093492(无效)
````
方法：
config-client的spring.application.name必须和自己的配置文件名相匹配。
例如配置文件为：
configservice-dev.properties
这个时候对应的config-cleint的spring.application.name=configservice
````