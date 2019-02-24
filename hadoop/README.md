### 设置本地host解析
```
#/etc/hosts
192.168.153.133 serverb
192.168.153.134 serverc
```

### 下载jdk和hadoop包
```
wget http://mirror.bit.edu.cn/apache/hadoop/common/hadoop-3.1.2/hadoop-3.1.2.tar.gz -O roles/bootstrap/files/hadoop-3.1.2.tar.gz
#jdk为oracle 1.8.0_201,请自行下载，下载后保存为 roles/bootstrap/files/jdk-8u201-linux-x64.tar.gz
```

### 初始化环境及生产配置文件
```
ansible-playbook -i host.ini bootstrap.yml
```

### 格式化集群
```
hdfs namenode -format
```

### 启动集群
```
ansible-playbook -i host.ini start-cluster.yml
```