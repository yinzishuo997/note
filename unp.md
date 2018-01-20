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


