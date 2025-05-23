# Introduction

[![rabbitmq-server-snap](https://snapcraft.io/rabbitmq-server-snap/badge.svg)](https://snapcraft.io/rabbitmq-server-snap)
[![rabbitmq-server-snap](https://snapcraft.io/rabbitmq-server-snap/trending.svg?name=0)](https://snapcraft.io/rabbitmq-server-snap)
[![CI](https://github.com/nicolasbock/rabbitmq-server-snap/actions/workflows/CI.yaml/badge.svg)](https://github.com/nicolasbock/rabbitmq-server-snap/actions/workflows/CI.yaml)
[![GitHub issues](https://img.shields.io/github/issues/nicolasbock/rabbitmq-server-snap)](https://github.com/nicolasbock/rabbitmq-server-snap/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/nicolasbock/rabbitmq-server-snap)](https://github.com/nicolasbock/rabbitmq-server-snap/pulls)

This is a repository for the snapped version of RabbitMQ.


## Content slots

This snap includes two content slots available for other snaps to use:

1) rabbitmq

This slot provides access to all of the contents of the snap package. This
allows other snaps to use the relevant binaries and libraries for using e.g.
rabbitmqctl, without a snap having to bundle its own (potentially incompatible)
binaries to communicate with the rabbitmq server.

2) cookie

This slot provides access to the automatically generated erlang cookie file
which is used to authenticate with the rabbitmq server instance. This is
required because all nodes communicating with a server must use the same cookie
file.


This snap can be declared as a `default-provider` in the plug declaraction of
a consumer snap to ensure that if no other snap satisfies the declared content
interface plugs, snapd will install or refresh this snap.

For more information on content interfaces, refer to [the documentation](https://snapcraft.io/docs/content-interface).
