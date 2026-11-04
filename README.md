# Home Assistant HashiCorp Vault Add-on

[![Add repository](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fmikenabhan%2Fhomeassistant-vault)

Add this repository in **Settings → Add-ons → Add-on Store → ⋮ → Repositories**, then install *HashiCorp Vault*.

Dependencies are first-party only: HashiCorp's `hashicorp/vault` image (binary) and Home Assistant's official add-on base image (bashio/s6).

## Versioning

The add-on version in `vault/config.yaml` is the bundled Vault version (e.g. `2.2.1`). Renovate bumps it together with the `hashicorp/vault` image in `vault/Dockerfile`.

To ship an add-on change without a Vault release, append a revision suffix: `2.2.1-1`, then `2.2.1-2`, and so on. When Renovate moves to a new Vault version it resets the version to plain `2.3.0`, dropping the revision.
