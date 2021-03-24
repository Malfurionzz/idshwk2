

**Task：** see two packets in a TCP flow with：

* first packet has “login” or “Initial” in payload, destination port is 3399;
* and second packet has a “IPv4Address:Port”string(E.g. 123.45.6.7:8080) in payload. destination port is
3399;
* output a alert with msg “bot founded” and sid 1000001

## brief record

本题中要求两个规则相互作用形成一个警报，首先考虑到使用activate/dynamic 规则，但查看手册可知：

```
Activate and Dynamic rules are phased out in favor of a combination of tagging (3.7.5) and flowbits (3.6.10).
```

因此改用flowbits 中的set 和isset来实现。

## 关于RE

在lzx大佬的指点之下，发现v1的RE写的不足

1. 端口为0-65535：`^([0-9]{1,4}|[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-9]{2}|655[0-2][0-9]|6553[0-5])$`

2. 一个RE的可视化网站：https://regexper.com/