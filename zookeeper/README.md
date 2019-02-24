### 下载zookeeper
```
wget http://mirror.bit.edu.cn/apache/zookeeper/zookeeper-3.4.13/zookeeper-3.4.13.tar.gz -O roles/deploy-zookeeper/files/zookeeper-3.4.13.tar.gz
```

### 部署zookeeper

```
ansible-playbook -i host.ini start-cluster.yml
```
