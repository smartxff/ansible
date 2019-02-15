### 下载spark文件
```
wget http://mirror.bit.edu.cn/apache/spark/spark-2.4.0/spark-2.4.0-bin-hadoop2.7.tgz -O spark/roles/deploy-spark/files/spark-2.4.0-bin-hadoop2.7.tgz
```

### 配置spark
```
cd spark
sed -i 's/spark-2.2.3-bin-hadoop2.7/spark-2.4.0-bin-hadoop2.7/' host.ini
```
## 执行ansible的机器到master和slave机器要免密
## master到slave机器也要免密

### 部署spark

```
ansible-playbook -i host.ini start-cluster.yml
```