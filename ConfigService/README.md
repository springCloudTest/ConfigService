# ConfigService

* /{application}/{profile}[/{label}]
* /{application}-{profile}.yml
* /{label}/{application}-{profile}.yml
* /{application}-{profile}.properties
* /{label}/{application}-{profile}.properties

上面的url会映射{application}-{profile}.properties对应的配置文件，{label}对应git上不同的分支，默认为master。

* testCase:
````
http://localhost:7001/configservice/prod

http://localhost:7001/configservice/prod/configservice-label
````

输出如下：
````
{"name":"configservice","profiles":["prod"],"label":"configservice-label","version":"833ec8b26872e5b21fca2af1675be08769e0f88d","propertySources":[]}
````
则配置没获取到git中的.properties



输出如下：
````
{"name":"configservice","profiles":["prod"],"label":"configservice-label","version":"833ec8b26872e5b21fca2af1675be08769e0f88d","propertySources":[{"name":"https://github.com/springCloudTest/ConfigService/config-repo/configservice-prod.properties","source":{"from":"git-prod-1.0"}},{"name":"https://github.com/springCloudTest/ConfigService/config-repo/configservice.properties","source":{"from":"git-default-1.0"}}]}
````
propertySources:为从配置文件中获取到的配置项