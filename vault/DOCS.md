# HashiCorp Vault

Runs the official `vault` binary with integrated Raft storage in the add-on's persistent `/data`.

## First start

Vault starts **uninitialized and sealed**. From a machine with the `vault` CLI:

```sh
export VAULT_ADDR=http://homeassistant.local:8200
vault operator init
vault operator unseal   # repeat with 3 of the 5 keys
```

Store the unseal keys and root token somewhere safe, **outside** Home Assistant. Vault must be unsealed again after every restart.

## Options

| Option | Description |
| --- | --- |
| `log_level` | trace, debug, info, warn, error |
| `ui` | Enable the web UI at `:8200/ui` |
| `tls_enabled` | Serve HTTPS using a certificate from Home Assistant's `/ssl` folder (e.g. from the Let's Encrypt or Duck DNS add-on) |
| `certfile` | Certificate file name inside `/ssl` (default `fullchain.pem`) |
| `keyfile` | Private key file name inside `/ssl` (default `privkey.pem`) |
| `api_addr` | Address clients use to reach Vault; defaults to the add-on hostname |

Note: port 8200 is exposed on the host; enable TLS or restrict access if your network is untrusted.
