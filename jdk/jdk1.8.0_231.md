---
description: Install
---

# JDK1.8.0\_231

## install jdk

```bash
mkdir /usr/local/java
tar xf /usr/local/src/jdk-8u231-linux-x64.tar.gz -C /usr/local/java/
ln -s /usr/local/java/jdk1.8.0_231 /usr/local/java/jdk
```

## set env

vim /etc/profile

```bash
export JAVA_HOME=/usr/local/java/jdk
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=$CLASSPATH:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar
```

