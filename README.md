# Nginx Load Balancer Example

This is a simple example of how to use the nginx-proxy

## Usage

#### App 1

```bash
docker build -t app1 .
docker run --name app1 -dp 5001:5000 app1
```

#### App 2

```bash
docker build -t app2 .
docker run --name app2 -dp 5002:5000 app2
```

### Nginx Proxy

```bash
 docker run --name nginx -dp 8082:80 load_balancer_nginx
```

## Test

```bash
while true; do curl http://localhost:8082 && sleep 2 && echo ""; done;
```
