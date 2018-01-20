### socket 函数

```c
#include <sys/socket.h>

int sokcet(int family, int type, int protocol);
```

|family（地址族）|说明             |
|-------------|:---------------:|
|AF_INET    |IPv4协议             |
|AF_INET6   |IPv6协议             |
|AF_LOCAL   |Unix域协议           |
|AF_ROUTE   |路由套接字           |
|AF_KEY     |密钥套接字           |
        
|type           |说明                |
|:-------------:|:------------------:|
|SOCK_STREAM    |字节流套接字         |
|SOCK_DGRAM     |数据包套接字         |
|SOCK_SEQPACKET |有序分组套接字      |
|SOCK_RAW       |原始套接字          |

|protocol   | 说明        |
|:----------:|:-----------:|
|IPPROTO_TCP | TCP          |
|IPPROTO_UDP|   UDP         |
|IPPROTO_SCTP| SCTP         |