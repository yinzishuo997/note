``` cpp
#include <netinet/in.h>

struct in_addr {
    in_addr_t   s_addr;         //network byte ordered 32-bit IPv4 address
};

struct sockaddr_in {
    uint8_t         sin_len;    // length of structure (16)
    sa_family_t     sin_family; // AF_INET
    in_port_t       sin_port    // 16-bit TCP or UDP port number 
    struct in_addr  sin_addr;   // network byte order 32-bit IPv4 address 
    char            sin_zero[8] // network byte order unused
};

struct sockaddr {
    uint8_t         sa_len;
    unsigned short  sa_family;  // address family, AF_XXX
    char            sa_data[14] // 14 bytes of protocol address
};
```

```cpp

#include <sys/types.h>

int8_t
uint8_t
int16_t
uint16_t
int32_t
uint32_t
```
```cpp
#include <sys/socket.h>

sa_family_t
socklen_t   // uint32_t
```
```cpp

#include <netinet/in.h>

in_addr_t   //ipv4地址, uint32_t
in_port_t   //TCP或UDP端口, uint16_t
```

### IPv6 套接字地址结构
```cpp

#include <netinet/in.h>

struct in6_addr {
    unit8_t s6_addr[16];
};

#define SIN6_LEN

struct sockaddr_in6 {
    unit8_t         sin6_len;       // length of this struct 28;
    sa_family_t     sin6_family;    // AF_INET6
    in_port_t       sin6_port;      // network byte ordered transport layer port
    uint32_t        sin6_flowinfo;  // flow information, undefined
    struct in6_addr sin6_addr;      // network byte ordered IPv6 address
    uint32_t        sin6_scope_id;  // set of interfaces for a scope
};

```

### 新的通用套接字地址结构
```cpp
#include <netinet/in.h>
struct sockaddr_storage {
    uint8_t     ss_len;
    sa_family_t ss_family
};


### 字节排序函数
```c
#include <netinet/in.h>

uint16_t htons(uint16_t host16bitvalue);
uint32_t htonl(uint32_t host32bitvalue);

uint16_t ntohs(uint16_t net16bitvalue);
uint32_t ntohl(uint32_t net32bitvalue);
```
