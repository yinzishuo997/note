### socket 函数

```c
#include <sys/socket.h>

int sokcet(int family, int type, int protocol);

| family    |说明           |
| --------- |-----------:   |
|AF_INET    | IPv4          |
|AF_INET6   | IPv6          |
|AF_LOCAL    | Unix域协议    |
|AF_ROUTE   |路由套接字      |
|AF_KEY     |密钥套接字      |
