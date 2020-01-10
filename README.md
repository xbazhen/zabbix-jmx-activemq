# pyjmx-discovery

Based on https://github.com/xbazhen/zabbix-jmx-activemq/.

我基于如下原因写了这个模板:
 1. 需要对ActiveMQ里面的一些内置信息做监控.
 2. 通过JMX直接监控ActiveMQ


Requirements
------------
- zabbix_server: 2.4.5  其他版本未做验证


Usage
------------
- 把模板导入到zabbix里面作为父模板
- 新建子模板，在模板管理里面，引用父模板
- 在相关子模板里重新设置宏变量

    Example:
```
{$JMX_USERNAME}    => username
{$JMX_PASSWORD}    => password
{$JMX_DOMAIN_NAME} => org.apache.activemq
```
- zabbix的web管理页面添加jmx监控项即可
- 详情数据参见 activemq_latest_data.png



Reference
------------
- activemq配置jmx：
http://activemq.apache.org/jmx.html
- 通过jolokia 获取activemq的API： http://www.jakubkorab.net/2013/11/monitoring-activemq-via-http.html
- 