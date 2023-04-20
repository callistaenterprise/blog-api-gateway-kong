# Managing APIs using Kong Gateway

## Overview

API gateways are becoming increasingly more popular, and for good reasons.
As the number of APIs within an organisation grows, the amount of "plumbing"
required to expose the APIs in a secure, efficient and maintainable way quickly
become overwhelming.

An API Gateway is an architectural pattern which introduces a transparent placeholder
between API clients and the APIs, where [Cross Cutting Concerns] such as Access
Control, Monitoring, Logging, Caching and Rate Limiting can be implemented.

This project complements my [blog series](https://callistaenterprise.se/blogg/teknik/2023/04/20/2023-04-20-kong-api-gateway-part1/)
on Managing API's using Kong Gateway.

## How to use this repository

The repository contains working dockerized configuration for the examples described in the blog.
The `kong-with-plugins/plugins` subfolder contains git submodules with various Open Source
Kong plugins used in the examples. In order to have these submodules checked-out, clone the repository
with the `--recursive` flag:

```
git clone --recursive https://github.com/callistaenterprise/blog-api-gateway-kong
```

## How to start the dockerized containers

Run the following command to start the dockerized containers:

```
docker compose up -d
```

Shut them down with the following command when done:

```
docker compose down
```

