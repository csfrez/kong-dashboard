# Kong Dashboard

[![Build Status](https://travis-ci.org/PGBI/kong-dashboard.svg?branch=3.0)](https://travis-ci.org/PGBI/kong-dashboard)

[**Kong**](https://getkong.org/) is a scalable, open source API Layer (also known as a API Gateway, or API Middleware).
Kong runs in front of any RESTful API and provide functionalities
and services such as requests routing, authentication, rate limiting, etc.

**Kong dashboard** is a GUI that will let you manage your Kong Gateway setup.

## Compatibility matrix

| Kong-Dashboard versions | Kong versions | Node versions |
|-----------|------------------------------|--------------|
| 1.x.x     | 0.6.x, 0.7.x, 0.8.x, 0.9.x   |              |
| 2.x.x     | 0.10.x                       |              |
| 3.0.x     | 0.9.x, 0.10.x, 0.11.x        | >= 6.0.0     |
| 3.x.x     | 0.9.x, 0.10.x, 0.11.x, 0.12.x| >= 6.0.0     |

## Prerequisites

You will need:

1. a running Kong gateway. https://getkong.org/install/
2. nodejs and npm, or docker

## Installation

### Using npm

```bash
# Install Kong Dashboard
npm install -g kong-dashboard

# Start Kong Dashboard
kong-dashboard start --kong-url http://kong:8001

# Start Kong Dashboard on a custom port
kong-dashboard start \
  --kong-url http://kong:8001 \
  --port [port]

# Start Kong Dashboard with basic auth
kong-dashboard start \
  --kong-url http://kong:8001 \
  --basic-auth user1=password1 user2=password2

# See full list of start options
kong-dashboard start --help
```

### Using Docker

[![](https://images.microbadger.com/badges/image/pgbi/kong-dashboard.svg)](https://microbadger.com/images/pgbi/kong-dashboard "Get your own image badge on microbadger.com")

```bash
# Start Kong Dashboard
docker run --rm -p 8080:8080 pgbi/kong-dashboard start --kong-url http://kong:8001

# Start Kong Dashboard on a custom port
docker run --rm -p [port]:8080 pgbi/kong-dashboard start --kong-url http://kong:8001

# Start Kong Dashboard with basic auth
docker run --rm -p 8080:8080 pgbi/kong-dashboard start \
  --kong-url http://kong:8001
  --basic-auth user1=password1 user2=password2

# See full list of start options
docker run --rm -p 8080:8080 pgbi/kong-dashboard start --help

# 后台启动
docker run -itd -p 8888:8080 pgbi/kong-dashboard start --kong-url http://10.1.108.119:8001
docker run -itd --name kong-dashboard -p 8888:8080 pgbi/kong-dashboard start --kong-url http://10.11.0.175:8001 

```


## Use

You can now browse Kong Dashboard at http://localhost:8080

# Contributing

If you consider contributing to Kong Dashboard by reporting a bug, or submitting a patch, please checkout the
[contribution document](./CONTRIBUTING.md) for guidance.
