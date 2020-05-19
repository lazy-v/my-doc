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

