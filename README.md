# docker-registery-mirror-compose
docker registry mirror server compose file


# Usage
## Securing your registry proxy cache
[ ] todo
## Create a v2 registry proxy cache configuration
```
mkdir data
docker run -it --rm --entrypoint cat registry:2 /etc/docker/registry/config.yml > ./data/config.yml
```

## Update the ‘http’ section to configure TLS:
```
http:
      tls:
            certificate: /var/lib/registry/domain.crt
            key: /var/lib/registry/domain.key
```

## Add a ‘proxy’ section to your configuration file to enable the cache
```
proxy:
      remoteurl: https://registry-1.docker.io
      username: [username]
      password: [password]
```    

## start
`docker-compose up -d`

# Client


# reference
- https://blog.docker.com/2015/10/registry-proxy-cache-docker-open-source/
