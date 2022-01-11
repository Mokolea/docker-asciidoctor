# docker-asciidoctor [![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/mokolea/asciidoctor)](https://hub.docker.com/r/mokolea/asciidoctor) [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/mokolea/asciidoctor/latest)](https://hub.docker.com/r/mokolea/asciidoctor)

Test AsciiDoc using Asciidoctor

[![Release](https://img.shields.io/github/release/Mokolea/docker-asciidoctor.svg)](https://github.com/Mokolea/docker-asciidoctor/releases)

## Asciidoctor
 - https://asciidoctor.org/
 - https://asciidoctor.org/docs/asciidoc-syntax-quick-reference/
 - https://asciidoctor.org/docs/user-manual/
 - https://asciidoctor.org/docs/asciidoctor-pdf/

Docker container based on:
 - [Asciidoctor Docker Container](https://github.com/asciidoctor/docker-asciidoctor)
 - [Asciidoctor Text Processor](https://github.com/asciidoctor/asciidoctor)
 - [Asciidoctor Project Site](https://github.com/asciidoctor/asciidoctor.org)

## Usage
 - Start new container from a current asciidoc-project directory: `$ docker run -it -v $(pwd):/data --name asciidoctor -h asciidoctor mokolea/asciidoctor:latest`
 - Optional: Set user and group IDs to override the default image user (1000:1000) by using parameter:
    - `-u root` for root user
    - `-u $(id -u):$(id -g)` for current host user (experimental - does not work without additional configuration)
 - Subsequent use of the same stopped container: `$ docker start -ai asciidoctor`
 - Create bash shell session in the already running container: `$ docker exec -it asciidoctor bash`

## Test
```
bash-5.1$ asciidoctor --version
Asciidoctor 2.0.15 [https://asciidoctor.org]
Runtime Environment (ruby 2.7.3p183 (2021-04-05 revision 6847ee089d) [x86_64-linux-musl]) (lc:UTF-8 fs:UTF-8 in:UTF-8 ex:UTF-8)
bash-5.1$ 

bash-5.1$ asciidoctor-pdf --version
Asciidoctor PDF 1.6.0 using Asciidoctor 2.0.15 [https://asciidoctor.org]
Runtime Environment (ruby 2.7.3p183 (2021-04-05 revision 6847ee089d) [x86_64-linux-musl]) (lc:UTF-8 fs:UTF-8 in:UTF-8 ex:UTF-8)
bash-5.1$ 

bash-5.1$ asciidoctor hello-world.adoc 
bash-5.1$ ls hello-world.html 
hello-world.html
bash-5.1$ 

bash-5.1$ asciidoctor-pdf hello-world.adoc 
bash-5.1$ ls hello-world.pdf 
hello-world.pdf
bash-5.1$ 
```

## TODO
 - Add hello-world.adoc

## Done
 - Setup appropriate user to not run tools (asciidoctor, asciidoctor-pdf, ...) as root and so not have generated files from root in host file system

-- Mario
