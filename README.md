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
    digest8_t digest;
    sha1_get_digest_bytes(&s, digest);
    for (size_t i = 0; i < sizeof(digest); ++i) {
        printf("%02x", digest[i]);
    }
    printf("\n");
    return 0;
}
```

```console
$ cc -o teenysha1test teenysha1test.c  && ./teenysha1test
$ printf 'hello' | sha1sum -
```
