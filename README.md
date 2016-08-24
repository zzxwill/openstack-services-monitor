# openstack-services-monitor
OpenStack服务监控及维护

Stage 1: Shell脚本执行各个服务命令查看
[root@a-node3 webconsole]# openstack compute service list
+----+------------------+---------+----------+---------+-------+----------------------------+
| Id | Binary           | Host    | Zone     | Status  | State | Updated At                 |
+----+------------------+---------+----------+---------+-------+----------------------------+
|  1 | nova-conductor   | a-node3 | internal | enabled | up    | 2016-08-24T02:27:41.000000 |
|  3 | nova-consoleauth | a-node3 | internal | enabled | up    | 2016-08-24T02:27:41.000000 |
|  4 | nova-scheduler   | a-node3 | internal | enabled | up    | 2016-08-24T02:27:41.000000 |
| 10 | nova-compute     | a-node3 | nova     | enabled | up    | 2016-08-24T02:27:41.000000 |
+----+------------------+---------+----------+---------+-------+----------------------------+

[root@a-node3 webconsole]# openstack compute agent list
(这个命令没有显示结果,可能是社区的Bug。)
[root@a-node3 webconsole]# neutron agent-list
+--------------------------------------+----------------------+---------+-------------------+-------+----------------+---------------------------+
| id                                   | agent_type           | host    | availability_zone | alive | admin_state_up | binary                    |
+--------------------------------------+----------------------+---------+-------------------+-------+----------------+---------------------------+
| 55f183e5-e34c-48df-ba66-734021ee5b65 | Linux bridge agent   | a-node3 |                   | :-)   | True           | neutron-linuxbridge-agent |
| a2414029-79aa-4fb3-8644-a6614c641b28 | L3 agent             | a-node3 | nova              | :-)   | True           | neutron-l3-agent          |
| af644385-859d-4169-9950-a23ef816eb4d | Loadbalancerv2 agent | a-node3 |                   | :-)   | True           | neutron-lbaasv2-agent     |
| b8f80af3-b5da-4e1c-b4d2-b7f53ab4ed0c | Metadata agent       | a-node3 |                   | :-)   | True           | neutron-metadata-agent    |
| baa7500a-eff0-42c4-a4c5-b59e933842e2 | DHCP agent           | a-node3 | nova              | :-)   | True           | neutron-dhcp-agent        |
+--------------------------------------+----------------------+---------+-------------------+-------+----------------+---------------------------+

