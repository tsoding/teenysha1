# TeenySHA1

A simple header only SHA1 implementation in pure C (no dependencies). Based on the implementation in boost::uuid::details. Translated from TinySHA1 https://github.com/mohaps/TinySHA1

SHA1 Wikipedia Page: http://en.wikipedia.org/wiki/SHA-1

## Usage

```c
#define TEENY_SHA1_IMPLEMENTATION
#include "teenysha1.h"

int main(void)
{
    const char *message = "hello";
    SHA1 s = {0};
    sha1_reset(&s);
    sha1_process_bytes(&s, message, strlen(message));
    uint32_t digest[5];
    sha1_get_digest(&s, digest);
    printf("%08x%08x%08x%08x%08x\n", digest[0], digest[1], digest[2], digest[3], digest[4]);
    return 0;
}
```
