# 三、证书环境准备

## 1、下载cfssl

```bash
curl -L 
https://pkg.cfssl.org/R1.2/cfssl_linux-amd64
 -o /usr/bin/cfssl
curl -L 
https://pkg.cfssl.org/R1.2/cfssljson_linux-amd64
 -o /usr/bin/cfssljson
curl -L 
https://pkg.cfssl.org/R1.2/cfssl-certinfo_linux-amd64
 -o /usr/bin/cfssl-certinfo
chmod +x /usr/bin/cfssl /usr/bin/cfssljson /usr/bin/cfssl-certinfo
```

## 2、创建ca证书目录及证书请求文件目录

```bash
mkdir -p /opt/ssl/csr
```

{% hint style="info" %}
etcd各个节点都需要执行
{% endhint %}



