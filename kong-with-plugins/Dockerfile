FROM kong:2.8.3
USER root

COPY ./plugins/kong-oidc /custom-plugins/kong-oidc
WORKDIR /custom-plugins/kong-oidc
RUN luarocks make

COPY ./plugins/kong-token-introspection /custom-plugins/kong-token-introspection
WORKDIR /custom-plugins/kong-token-introspection
RUN luarocks make

COPY ./plugins/kong-plugin-mtls-auth /custom-plugins/kong-plugin-mtls-auth
WORKDIR /custom-plugins/kong-plugin-mtls-auth
RUN luarocks make

COPY ./plugins/kong-plugin-mtls-acl /custom-plugins/kong-plugin-mtls-acl
WORKDIR /custom-plugins/kong-plugin-mtls-acl
RUN luarocks make

USER kong
WORKDIR /
