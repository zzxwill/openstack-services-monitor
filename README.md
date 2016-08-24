**openstack-services-monitor**
==========================
OpenStack服务监控及维护

Stage 1: Shell脚本执行OpenStack命令检测服务
------------------------------------------
- openstack compute service list (nova service-list)

::

 $ openstack compute service list
 +----+------------------+---------+----------+---------+-------+----------------------------+
 | Id | Binary           | Host    | Zone     | Status  | State | Updated At                 |
+----+------------------+---------+----------+---------+-------+----------------------------+
|  1 | nova-conductor   | a-node3 | internal | enabled | up    | 2016-08-24T02:27:41.000000 |
|  3 | nova-consoleauth | a-node3 | internal | enabled | up    | 2016-08-24T02:27:41.000000 |
|  4 | nova-scheduler   | a-node3 | internal | enabled | up    | 2016-08-24T02:27:41.000000 |
| 10 | nova-compute     | a-node3 | nova     | enabled | up    | 2016-08-24T02:27:41.000000 |
+----+------------------+---------+----------+---------+-------+----------------------------+

- openstack compute agent list (neutron agent-list)

[root@a-node3 webconsole]# openstack compute agent list

Stage 2: 调用Open-Falcon或Zabbix API
--------------------------------

Stage 3: 调研OpenStack社区是否原生支持
-----------------------------------