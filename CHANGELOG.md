# CHANGELOG

Version numbers correspond to Maubot version numbers in compatibility.

## unreleased

Added `maubot_docker_restart_policy` config option.

## v0.4.1

**Breaking change**. Maubot has removed the possibility to override the API base path,
so you always need to route `/_matrix/maubot/v1` to Maubot on the domain it is on.

Setting `maubot_server_base_path` has been removed.

## v0.3.1

First tagged version.
