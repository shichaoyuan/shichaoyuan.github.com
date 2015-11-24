---
layout: post
title: Reading Notes - Prudent Engineering Practice for Cryptographic Protocols
date: 2015-07-10 22:06:59
tags: security
---

##1

最近在做一个关于支付的小需求，其中有个关于支付密码的地方，由于运维短时间内提供不了HTTPS，所以需要设计一个简单的加密协议，保证密码不能泄露，不能被重放攻击。

如何做？

使用RSA算法，客户端内置一个公钥（或者动态获取），服务器保存一个私钥，

```plain
1. server -------------nonce-----------> client
2. server <---encrypt(passowrd+nonce)--- client

server decrypt(message) and check(password+nonce)
```

当然密码存储不当也存在泄露的问题，解决这个问题可以使用PBKDF2([rfc2898](https://tools.ietf.org/html/rfc2898))。至于迭代次数可以参考stackexchange中的这个[问题](http://security.stackexchange.com/questions/3959/recommended-of-iterations-when-using-pkbdf2-sha256)。

另外终端安全坑太大，暂时不考虑。

然后又想起读书的时候上《安全协议》那门课读的那些论文，其中有一篇感觉相当经典，所以又找出来读了一遍。

##2

[Prudent Engineering Practice for Cryptographic Protocols](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=481513&filter%3DAND%28p_IS_Number%3A10294%29)

### Principle 1


### Principle 2

### Principle 3
>If the identity of a principal is essential to the meaning of a message, it is prudent to mention the principal’s name explicitly in the message.

### Principle 4
### Principle 5

### Principle 6

### Principle 7

### Principle 8
>If timestamps are used as freshness guarantees by reference to absolute time, then the difference between local clocks at various machines must be much less than the allowable age of a message deemed to be valid. Furthermore, the time maintenance mechanism everywhere becomes part of the trusted computing base.

### Principle 9

### Principle 10

### Principle 11