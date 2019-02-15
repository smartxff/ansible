### 下载kafka
```
wget wget http://mirror.bit.edu.cn/apache/kafka/2.1.0/kafka_2.11-2.1.0.tgz -O kafka/roles/deploy-kafka/files/kafka_2.11-2.1.0.tgz
```

### 部署kafka

```
ansible-playbook -i host.ini start-cluster.yml
```