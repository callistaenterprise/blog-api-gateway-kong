# kong-with-plugins
A containerised Kong gateway image using [declarative configuration in DB-less mode](https://docs.konghq.com/gateway/latest/production/deployment-topologies/db-less-and-declarative-config/)
configured with custom plugins:

 * [OIDC plugin](https://github.com/nokia/kong-oidc)
 * [token-introspection plugin](https://github.com/VentaApps/kong-token-introspection)
 * [mtls-auth plugin](https://github.com/callistaenterprise/kong-plugin-mtls-auth)
 * [mtls-acl plugin](https://github.com/callistaenterprise/kong-plugin-mtls-acl)

## Building the custom docker image 
For simplicity, the source code for the plugins are included in the `plugins` folder, using git submodules. To bootstrap
the submodules, issue the following command:

```
git submodule update --init --recursive
```

Then build the custom image using the following command:

```
docker build -t kong-with-plugins:latest .
```

## Configuring the custom docker image 
Mount configuration files into the container, using docker-compose:

```
    volumes:
      - ./kong.yml:/etc/kong/kong.yml
      - ./kong.conf:/etc/kong/kong.conf
```

If the configuration files refers to certificates, mount these files/folders as well:

```
    volumes:
      - ../certs:/etc/kong/ssl
```
