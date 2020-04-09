# Https

**基于Http协议，增加TLS协议的实现，从而保障数据的安全性**

### TLS协议

#### TLS1.2握手流程

* 2次RTT
* ClientHello：发送支持的加密方法、随机数1
* ServerHello：返回选择的加密方法、随机数2、服务端证书
* ClientFinished：校验证书，再生成随机数3，用服务端公钥加密传输，生成摘要，结束密钥交换流程，如果服务端需要客户端证书则传，后续都用密钥加密通信
* ServerFinished：服务端使用3个随机数生成密钥，对握手过程生成摘要，发送结束消息

#### TLS1.3握手流程

* 1次RTT
* ClientHello：获取上次的密钥，并且加密这次的内容
* ServerHello：用上次的密钥解密，如果认为过期，告诉客户端重新协商
* 0次RTT：使用前一次加密通信建立后传送的密钥进行加密，在密钥协商的第一次发送时，就把加密的数据进行传输

### 优缺点

* 优点：安全
* 缺点：增加了握手次数，访问速度变慢了