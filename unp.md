``` cpp
#include <netinet/in.h>

struct sockaddr_in {
    uint8_t         sin_len;    // length of structure (16)
    sa_family_t     sin_family; // AF_INET
    in_port_t       sin_port    // 16-bit TCP or UDP port number
    struct in_addr  sin_addr;   // network byte order 
                                // 32-bit IPv4 address
    char            sin_zero[8]
}

```