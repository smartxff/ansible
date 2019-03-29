### 部署单节点的mysql
```
ansible-playbook -i hosts.single deploy-mysql57-offline.yml
ansible-playbook -i hosts.single start-single.yml
```

### 部署主从集群mysql
#### 启动并配置master
```
ansible-playbook -i hosts.cluster deploy-mysql57-offline.yml
ansible-playbook -i hosts.cluster start-master.yml 


```
#### 查看输出的binlog文件名和position，填入hosts.cluster
ok: [172.17.0.5] => {
    "msg": "File\tPosition\tBinlog_Do_DB\tBinlog_Ignore_DB\tExecuted_Gtid_Set\nmysql-bin.000002\t991\t\t\t"
}
其中 binlog文件名为：mysql-bin.000002
position为：991
即hosts.cluster设置为
POSITION=991
BINLOGFILENAME=mysql-bin.000002
```
ansible-playbook -i hosts.cluster start-slave.yml
```
