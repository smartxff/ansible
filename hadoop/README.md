### 设置本地host解析

```
namenode 要相互可以免密ssh
```

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

### 下载hbase包
```
wget http://archive.apache.org/dist/hbase/1.3.1/hbase-1.3.1-bin.tar.gz -O roles/install-hbase/files/hbase-1.3.1-bin.tar.gz
```

### 一.以本地文件系统启动单节点hbase
```
ansible-playbook -i example/host.single.hbase.ini start-hbase.yml
```

### 二.集群版
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

### 三。高可用集群版
#### 必须首先安装zookeeper,然后把zookeeper的地址填入host-ha.ini中

#### 部署hadoop程序，初始化hdfs，启动ha的namenode
```
ansible-playbook -i host-ha.ini bootstrap.yml
```
#### 部署datanode
```
ansible-playboot -i host-ha.ini bootstrap.yml
```


