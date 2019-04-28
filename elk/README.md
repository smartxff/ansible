### 下载es kibana
```
wget https://artifacts.elastic.co/downloads/kibana/kibana-6.0.0-x86_64.rpm -O roles/deploy-kibana/files/kibana-6.0.0-x86_64.rpm
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.0.0.rpm -O roles/deploy-elasticsearch/files/elasticsearch-6.0.0.rpm
```

### 部署es和kibana服务

```
ansible-playbook -i hosts deploy-all.yml 
```

### 启动服务
```
ansible-playbook -i hosts start-es.yml
ansible-playbook -i hosts start-kibana.yml
```
