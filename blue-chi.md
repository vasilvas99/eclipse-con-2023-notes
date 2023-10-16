# BlueChi

Developed by RedHat

Manage multi-node workloads and their dependencies for highly-regulated ecosystems.

## Concept

Systemd controls local services

BlueChi adds a thin layer to enable remote service management.

You define dependencies between services running on different nodes.

## Components

Controller -> controlling the connected agenents, **no state** management:
    - Does not define desired state
    - "Facilitator" for external applications to reach desired state
    - State mngr (external) connects over dbus to controller

Agent -> Running on each managed machine, managed by systemd:
    - Cannot interfere with other agents
    - p2p connection with controller

## Extra features

- Proxy services for resolving cross node dependencies
- quadlet -  run containers under systemd in an optimal way (podman)
- typed python binding for BlueChi Api, but otherwise over dbus
