# BIND9

#### cat /etc/named.conf

```text
options {
        listen-on port 53 { 172.30.50.100; };
        directory       "/var/named";
        dump-file       "/var/named/data/cache_dump.db";
        statistics-file "/var/named/data/named_stats.txt";
        memstatistics-file "/var/named/data/named_mem_stats.txt";
        recursing-file  "/var/named/data/named.recursing";
        secroots-file   "/var/named/data/named.secroots";
        allow-query     { any; };
        forwarders      { 114.114.114.114; };
        recursion yes;
        dnssec-enable no;
        dnssec-validation no;
        bindkeys-file "/etc/named.root.key";
        managed-keys-directory "/var/named/dynamic";
        pid-file "/run/named/named.pid";
        session-keyfile "/run/named/session.key";
};

logging {
        channel default_debug {
                file "data/named.run";
                severity dynamic;
        };
};

zone "." IN {
        type hint;
        file "named.ca";
};

include "/etc/named.rfc1912.zones";
include "/etc/named.root.key";
```

#### cat /etc/named.rfc1912.zones

{% hint style="info" %}
add to tail of file
{% endhint %}

```text
zone "host.com" IN {
        type    master;
        file    "host.com.zone";
        allow-update { 172.30.50.100; };
};

zone "pro.com" IN {
        type    master;
        file    "pro.com.zone";
        allow-update { 172.30.50.100; };
};
```

#### cat /var/named/host.com.zone

```text
$ORIGIN host.com.
$TTL 600    ; 10 minutes
@            IN SOA    dns1.host.com. cd_liuw.sina.com. (
                2020052000 ; serial
                10800      ; refresh (3 hours)
                900        ; retry (15 minutes)
                604800     ; expire (1 week)
                86400      ; minimum (1 day)
                )
        NS      dns1.host.com.
$TTL 60    ; 1 minute
dns1                       A    172.30.50.100
tj-53-87                   A    172.30.53.87
tj-50-222                  A    172.30.50.222
```

#### cat /var/named/pro.com.zone

```text
$ORIGIN pro.com.
$TTL 600    ; 10 minutes
@            IN SOA    dns1.pro.com. cd_liuw.sina.com. (
                2020052001 ; serial
                10800      ; refresh (3 hours)
                900        ; retry (15 minutes)
                604800     ; expire (1 week)
                86400      ; minimum (1 day)
                )
        NS      dns1.pro.com.
$TTL 60    ; 1 minute
dns1                       A    172.30.50.100
www                        A    172.30.53.87
```

