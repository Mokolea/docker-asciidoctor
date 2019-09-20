# docker-asciidoctor [![Size](https://img.shields.io/microbadger/image-size/mokolea/asciidoctor.svg)](https://hub.docker.com/r/mokolea/asciidoc) [![Layers](https://img.shields.io/microbadger/layers/mokolea/asciidoc.svg)](https://hub.docker.com/r/mokolea/asciidoctor)

Test Asciidoctor

[![Release](https://img.shields.io/github/release/Mokolea/docker-asciidoctor.svg)](https://github.com/Mokolea/docker-asciidoctor/releases)

## Asciidoctor
 - https://asciidoctor.org/
 - https://asciidoctor.org/docs/
 - https://asciidoctor.org/docs/asciidoctor-pdf/
 - https://asciidoctor.org/docs/asciidoc-syntax-quick-reference/
 - https://asciidoctor.org/docs/user-manual/
 - ...

## Usage
 - Start container from current asciidoc-project directory: `$ docker run -it -v $(pwd):/data --name asciidoctor -h asciidoctor mokolea/asciidoctor:latest`
 - Optional: Set user and group IDs to override the default image user (1000:1000) by using parameter:
    - `-u root` for root user
    - `-u $(id -u):$(id -g)` for current host user (experimental - does not work without additional configuration)
 - Subsequent use of the same container: `$ docker start -ai asciidoctor`
 - Start bash shell in the already running container: `$ docker exec -it asciidoctor bash`

## Test
```
bash-5.0$ asciidoctor --version
Asciidoctor 2.0.10 [https://asciidoctor.org]
Runtime Environment (ruby 2.5.5p157 (2019-03-15 revision 67260) [x86_64-linux-musl]) (lc:UTF-8 fs:UTF-8 in:UTF-8 ex:UTF-8)
bash-5.0$ 

bash-5.0$ asciidoctor-pdf --version
Asciidoctor PDF 1.5.0.beta.5 using Asciidoctor 2.0.10 [https://asciidoctor.org]
Runtime Environment (ruby 2.5.5p157 (2019-03-15 revision 67260) [x86_64-linux-musl]) (lc:UTF-8 fs:UTF-8 in:UTF-8 ex:UTF-8)
bash-5.0$ 

bash-5.0$ asciidoctor hello-world.adoc 
bash-5.0$ 

bash-5.0$ asciidoctor-pdf hello-world.adoc 
bash-5.0$ 
```

## TODO
 - Add hello-world.adoc

## Done
 - Setup appropriate user to not run tools (asciidoctor, asciidoctor-pdf, ...) as root and so not have generated files from root in host file system

-- Mario