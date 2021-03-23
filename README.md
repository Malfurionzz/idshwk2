

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