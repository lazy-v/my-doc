# Install

## deploy jdk\_1.8 env

## download zookeeper

```text
wget https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.6.1/apache-zookeeper-3.6.1-bin.tar.gz
```

## install zk

```text
tar xf /usr/local/src/apache-zookeeper-3.6.1-bin.tar.gz -C /opt/
ln -s /opt/apache-zookeeper-3.6.1-bin/ /opt/zookeeper
```

## create dir

```text
mkdir -p /data/zookeeper/data /data/zookeeper/logs
```

## modify config file

#### vim /opt/zookeeper/conf/zoo.cfg

```text
tickTime=2000
initLimit=10
syncLimit=5
dataDir=/data/zookeeper/data
dataLogDir=/data/zookeeper/logs
clientPort=2181
server.1=zk1.pro.com:2888:3888
server.2=zk2.pro.com:2888:3888
server.3=zk3.pro.com:2888:3888
```

## modify dns

## add myid

vim /data/zookeeper/data/myid

1 2 3

## start zk

/opt/zookeeper/bin/zkServer.sh start



