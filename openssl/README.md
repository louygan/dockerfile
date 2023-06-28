# detail info of tags
<br/>

| tag   |alpine version| comment             |
|-------|--------------|---------------------|
| 1.0.2u| 3.8          |                     |
| 1.1.1c| 3.9          | entrypoint: openssl |
| 1.1.1f|              | build, based on 3.10|
| 1.1.1h|              | build, based on 3.10|
| 1.1.1k| 3.9          |                     |
| 1.1.1l| 3.11         |                     |
| 1.1.1o| 3.12         |                     |
| 1.1.1q|              | build, based on 3.10|
| 1.1.1s| 3.13         |                     |
| 1.1.1t| 3.14         |                     |
| 1.1.1u| 1.15         |                     |
| 3.0.0 |              | build, based on 3.10|
| 3.0.8 | 3.17         |                     |
| 3.1.0 |              | build, based on 3.10|
| 3.1.1 | 3.18         |                     |
|       |              |                     |
|       |              |                     |
|       |              |                     |
|       |              |                     |
|       |              |                     |

refer to https://hub.docker.com/r/louygan/openssl-alpine/tags
<br/>

# how to build from source

use the Dockerfile in build directory.

## steps:  
  cd build  
  export VERSION=3.1.0  
  make
