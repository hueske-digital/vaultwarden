# Vault

This repository contains Vaultwarden – an integrated open source password management solution.

## Setup instructions

Setup a host in Caddy pointing to port 80. 

```
# EXTERNAL SERVICE WITH CLOUDFLARE PROXY #

https://vault.example.com {

    # import logging
    import cloudflare
    import tls
    import compression
    import header

    # enable this rule after configuration
    # handle @cloudflare {
    #     respond /admin* 404
    # }

    handle @cloudflare {
        reverse_proxy vault-app-1:80
    }
    respond 403
}
```
