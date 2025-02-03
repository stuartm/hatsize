# Hatsize

![ci](https://github.com/juanfont/headscale/actions/workflows/test.yml/badge.svg)

An improved version of Headscale, an open source, self-hosted implementation of the Tailscale control server.

**Note:** Always select the same GitHub tag as the released version you use
to ensure you have the correct example configuration and documentation.
The `main` branch might contain unreleased changes.

## What is Tailscale

Tailscale is [a modern VPN](https://tailscale.com/) built on top of
[Wireguard](https://www.wireguard.com/).
It [works like an overlay network](https://tailscale.com/blog/how-tailscale-works/)
between the computers of your networks - using
[NAT traversal](https://tailscale.com/blog/how-nat-traversal-works/).

Everything in Tailscale is Open Source, except the GUI clients for proprietary OS
(Windows and macOS/iOS), and the control server.

The control server works as an exchange point of Wireguard public keys for the
nodes in the Tailscale network. It assigns the IP addresses of the clients,
creates the boundaries between each user, enables sharing machines between users,
and exposes the advertised routes of your nodes.

A [Tailscale network (tailnet)](https://tailscale.com/kb/1136/tailnet/) is private
network which Tailscale assigns to a user in terms of private users or an
organisation.

## Design goal

Hatsize aims to implement a better self-hosted, open source alternative to the proprietary Tailscale control server than is currently available in Headscale.

## Supporting Hatsize

In good time we'll provide information on how you can support our efforts, but for now, the greatest contribution you can make would be your ideas, your time and your code!

## Features

For now see Headscale's feature page for an idea of where we're starting from. However please expect this list to grow beyond Headscale's narrow scope.

["Features" in the Headscale documentation](https://headscale.net/stable/about/features/).

## Client OS support

Coming soon.

## Running headscale

**Please note that we actively encourage you to deploy and use Headscale as you see fit, whether that be in a container or not! We obviously cannot provide individual support for every possible variation, but we will accept patches where necessary to support the environment of your chosing.**

Documentation will be coming in the near future once we have a stable release.

## Disclaimer

This project is not associated with Tailscale Inc or Headscale but is an independent effort using Headscale as a starting point.

The underlying principle is to serve the community by providing what they actually want from an open source, self-hosted Tailscale control server.

## Contributing

It's still very early days. Contributors are welcome but at this time no formal rules, coding standards etc have been developed. Watch this space!

Install and activate:

```shell
nix develop
```

### Testing and building

Some parts of the project require the generation of Go code from Protobuf
(if changes are made in `proto/`) and it must be (re-)generated with:

```shell
make generate
```

**Note**: Please check in changes from `gen/` in a separate commit to make it easier to review.

To run the tests:

```shell
make test
```

To build the program:

```shell
nix build
```

or

```shell
make build
```

## Contributors

Hatsize is based upon Headscale.
