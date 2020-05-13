# centos7 docker安装

## 系统环境

Centos7.8.2003

### 卸载旧版本

```text
yum remove docker \
docker-client \
docker-client-latest \
docker-common \
docker-latest-logrotate \
docker-selinux \
docker-engine-selinux \
docker-engine
```

### 安装依赖包

```text
yum install -y yum-utils device-mapper-persistent-data lvm2
```

### 添加docker-repository

```text
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

#### 查询docker可供安装版本

```text
yum list docker-ce --showduplicates | sort -r
```

### 安装最新版本

```text
yum install docker-ce docker-ce-cli containerd.io -y
```

### 启动服务与测试

```text
systemctl start docker && systemctl status docker && systemctl enable docker
docker run hello-world
```



