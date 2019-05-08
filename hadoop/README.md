### 设置本地host解析
```
#/etc/hosts
192.168.153.133 serverb
192.168.153.134 serverc
```

### 下载jdk和hadoop包
```
wget http://mirror.bit.edu.cn/apache/hadoop/common/hadoop-3.1.2/hadoop-3.1.2.tar.gz -O roles/install-hadoop/files/hadoop-3.1.2.tar.gz
#jdk为oracle 1.8.0_201,请自行下载，下载后保存为 roles/install-java/files/jdk-8u201-linux-x64.tar.gz
```

### 初始化环境及生产配置文件
```
ansible-playbook -i host.ini bootstrap.yml
```

### 1. 启动集群
```
ansible-playbook -i host.ini start-cluster.yml
```

### 2.只启动hdfs,不启动hadoop
```
ansible-playbook -i host.ini start-hdfs-only.yml 
```


flink

#### 下载flink 到 roles/flink/files/flink-1.7.0-bin-hadoop28-scala_2.12.tgz
```
ansible-playbook -i host.ini start-flink.yaml
```
