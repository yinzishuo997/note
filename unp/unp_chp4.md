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
        
<html>
    <body>
        <table border = "1">
            <caption align = "center"> socket函数的type常值 </caption>
            <tr>
                <th> type </th>
                <th> 说明 </th>
            </tr>
            <tr>
                <td> SOCK_STREAM </td>
                <td> 字节流套接字 </td>
            </tr>
            <tr>
                <td> SOCK_DGRAM </td>
                <td> 数据报套接字</td>
            </tr>
            <tr>
                <td> SOCK_SEQPACKET </td>
                <td> 有序分组套接字  </td>
            </tr>
            <tr>
                <td> SOCK_RAW   </td>
                <td> 原始套接字  </td>
            </tr>
        </table>
    </body>
</html>