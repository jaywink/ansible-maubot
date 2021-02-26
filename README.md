# Ansible Maubot

Matrix Maubot using Docker.

Runs and configures a single Maubot instance, optionally using an existing
account. If not using an existing account, you need to set up one using the
Maubot CLI commands.

Traefik friendly via Docker container labels.

## Configuration

### Required

```yaml
maubot_admin_password: settosomethingsupersecret
maubot_homeserver_name: domain.tld
maubot_homeserver_url: https://matrix.domain.tld
maubot_domain: maubot.domain.tld
maubot_synapse_registration_shared_secret: secretthing
maubot_unshared_secret: changemetosomethingsecret
```

### Client

Set these if using an existing account.

```yaml
# This only inserts the client the first time - it does not
# overwrite any values changed via the management interface!
# NOTE! Only supports debian based systems currently.
maubot_client_mxid: @maubot:domain.tld
maubot_client_access_token: secretthing
# Required if encrypted message support is needed
maubot_client_device_id: ABCDEFGH
# Optional
maubot_client_displayname: Maubot
maubot_client_avatar_url: mxc://domain.tld/etc
```

### Optional

These defaults will be used if not set.

```yaml
maubot_admin_username: admin
# While this is a custom build, any upstream builds also work
maubot_docker_image: jaywink/maubot:dev1
# Use for example to hook up with Traefik
maubot_docker_labels: []
# Docker network to attach to
maubot_docker_network: default
# Paths for the management page and API
maubot_server_base_path: "/maubot/api/v1"
maubot_server_ui_base_path: "/maubot"
maubot_server_plugin_base_path: "/maubot/plugin/"
```

## License

Apache 2.0
