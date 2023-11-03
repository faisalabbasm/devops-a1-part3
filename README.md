# devops-a1-part3

# command - docker volume create my_volume

# command - docker build -t nginx .

# output

=> [internal] load .dockerignore 0.0s
=> => transferring context: 2B 0.0s
=> [internal] load build definition from Dockerfile 0.0s
=> => transferring dockerfile: 58B 0.0s
=> [internal] load metadata for docker.io/library/nginx:latest 5.0s
=> [auth] library/nginx:pull token for registry-1.docker.io 0.0s
=> [1/1] FROM docker.io/library/nginx@sha256:86e53c4c16a6a276b204b0fd3a8143d86547c967dc8258b3d47c3a21bb68d3c6 10.3s
=> => resolve docker.io/library/nginx@sha256:86e53c4c16a6a276b204b0fd3a8143d86547c967dc8258b3d47c3a21bb68d3c6 0.0s
=> => sha256:565211f0ec2c97f4118c0c1b6be7f1c7775c0b3d44c2bb72bd32983a5696aa6a 1.78kB / 1.78kB 0.0s
=> => sha256:4de1e03138306e8db48a4ecbfb61e90ad3ed23a354bbcaaed0b356ca5c8703ea 626B / 626B 0.5s
=> => sha256:7745719004b6670d598243f7b0dabb7a31634e1ddd1eab8770750bf42e763240 958B / 958B 0.6s
=> => sha256:86e53c4c16a6a276b204b0fd3a8143d86547c967dc8258b3d47c3a21bb68d3c6 1.86kB / 1.86kB 0.0s
=> => sha256:81be38025439476d1b7303cb575df80e419fd1b3be4a639f3b3e51cf95720c7b 8.16kB / 8.16kB 0.0s
=> => sha256:f1359798dfe4f8f1f079a48a0aeeba1137c82f6f835606bd259f905f5ce4dc8b 38.05MB / 38.05MB 9.5s
=> => sha256:0eb0ed12e64c9900532fec4633caa1ee634bb9a5e9d2b49b23e8665c9ffd1a40 1.21kB / 1.21kB 1.0s
=> => sha256:0f17732d34d586e368500b12bc4310d2bdf9bfbccfb23ab1643db0239fd37d9d 369B / 369B 1.0s
=> => sha256:5836f8c1cebcc335d66e7461853897e9b83e17a547c867b4e2297957f6adf988 1.40kB / 1.40kB 1.5s
=> => extracting sha256:f1359798dfe4f8f1f079a48a0aeeba1137c82f6f835606bd259f905f5ce4dc8b 0.6s
=> => extracting sha256:4de1e03138306e8db48a4ecbfb61e90ad3ed23a354bbcaaed0b356ca5c8703ea 0.0s
=> => extracting sha256:7745719004b6670d598243f7b0dabb7a31634e1ddd1eab8770750bf42e763240 0.0s
=> => extracting sha256:0f17732d34d586e368500b12bc4310d2bdf9bfbccfb23ab1643db0239fd37d9d 0.0s
=> => extracting sha256:0eb0ed12e64c9900532fec4633caa1ee634bb9a5e9d2b49b23e8665c9ffd1a40 0.0s
=> => extracting sha256:5836f8c1cebcc335d66e7461853897e9b83e17a547c867b4e2297957f6adf988 0.0s
=> exporting to image 0.0s
=> => exporting layers 0.0s
=> => writing image sha256:780873d842c13fae8bae8a9bd475f77e697488bb1e17399fe5fc8dd24c1aa8b1 0.0s
=> => naming to docker.io/library/nginx

# command - docker run -d -p 8081:80 --name volume_container -v my_volumn:/var/lib nginx

# output

dfd59d814380fd73d0b613096b3d656f3d5df23661990666621436855d74b4c9

# command - docker cp index.html volume_container:/usr/share/nginx/html

Successfully copied 2.05kB to volume_container:/usr/share/nginx/html

# command - docker stop volume_container

# output

volume_container

# command - docker rm volume_container

# output

volume_container

# command - docker build -t httpd .

# output - => [internal] load build definition from Dockerfile 0.0s

=> => transferring dockerfile: 58B 0.0s
=> [internal] load .dockerignore 0.0s
=> => transferring context: 2B 0.0s
=> [internal] load metadata for docker.io/library/httpd:latest 5.0s
=> [auth] library/httpd:pull token for registry-1.docker.io 0.0s
=> [1/1] FROM docker.io/library/httpd@sha256:4e24356b4b0aa7a961e7dfb9e1e5025ca3874c532fa5d999f13f8fc33c09d1b7 9.7s
=> => resolve docker.io/library/httpd@sha256:4e24356b4b0aa7a961e7dfb9e1e5025ca3874c532fa5d999f13f8fc33c09d1b7 0.0s
=> => sha256:032af99592618d77a391821b7ada3d1917c274a34a62688c847de8a7b017bfbc 1.37kB / 1.37kB 0.0s
=> => sha256:4b97e7eb136b2edd4f5bc504db52fc8f88b8528c418c404b478c6794f9e0eb35 9.11kB / 9.11kB 0.0s
=> => sha256:db8fc7b4e131239974854debefcd15adaa8dc10e5faca5bb9ff80f6c69f7dad9 178B / 178B 0.5s
=> => sha256:b7b6cd577ff43b4fb8b2234c240ef2a1ecfe19ec0a17161253716b375ec457cb 4.02MB / 4.02MB 7.6s
=> => sha256:34532ee3d673607aacdf81b0bf706dbf7aebe5b67c11bdcf76fe874420d1e6fd 30.37MB / 30.37MB 8.8s
=> => sha256:4e24356b4b0aa7a961e7dfb9e1e5025ca3874c532fa5d999f13f8fc33c09d1b7 1.86kB / 1.86kB 0.0s
=> => extracting sha256:db8fc7b4e131239974854debefcd15adaa8dc10e5faca5bb9ff80f6c69f7dad9 0.0s
=> => sha256:44aebbdfc447faea32ba88a16d6e6900b125076dacf7cfd903980d93c6981cbb 298B / 298B 1.1s
=> => extracting sha256:b7b6cd577ff43b4fb8b2234c240ef2a1ecfe19ec0a17161253716b375ec457cb 0.2s
=> => extracting sha256:34532ee3d673607aacdf81b0bf706dbf7aebe5b67c11bdcf76fe874420d1e6fd 0.8s
=> => extracting sha256:44aebbdfc447faea32ba88a16d6e6900b125076dacf7cfd903980d93c6981cbb 0.0s
=> exporting to image 0.0s
=> => exporting layers 0.0s
=> => writing image sha256:bbb51b8b3340ab3d7799efbd7fa02502c0352a79e30bb3f0579cbd5c37bb0704 0.0s
=> => naming to docker.io/library/httpd

# command - docker run -d -p 8081:80 --name httpd_volume_container -v my_volumn:/usr/local/apache2/htdocs httpd

# output

a765bcc5cc2ec21d9bc948dfea97acecb0b93419db56c341bedd3a5bcdcdb940
