# Client-proxy environment

Client-proxy environment is a docker-compose environment that allows you to run a client behind of http/https proxy.

## How to use

In order to use this environment, you need to have docker, docker-compose and openssl installed.

Steps to run the environment:
1. Navigate to `common` directory and run the command:
```
openssl req -nodes -new -x509 -out ca.crt -keyout ca.key -config req.conf -extensions 'v3_req'
```
2. Run the command:
```
docker-compose build && docker-compose up
```
3. Run `docker exec -it CONTAINER_ID bash` to enter the client container. The container has no internet connection, unless you use the proxy.
4. Now, in order to use the proxy, the http proxy address is `http://proxy:8080` and the https proxy address is `https://proxy:443`. For example, if you want to access google.com, you can run the command:
```
curl --proxy http://proxy:8080 https://google.com
```
