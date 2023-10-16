# Ankaios

Workload orchestrator:

- You need one server node to for the cluster
- Multiple agents
- Agents can be dynamically connected to the server
- On startup server reads the initial config and is distributed to the agents
- ank cli for debugging

## Overview of agents

Each agent can manage multiple runtimes (native, containerized). You can specify start-up order between applications throughout the whole cluster.

Health manager app for example can update dynamically monitor the cluster.

## Requirements tracing/testing

Ankaios provides requirements tracing on GitHub.

- Comprehensive testing with rust unit tests
- RobotFramework for integration tests

## Upcoming

- k3s manifests support
- dep management
- authentication between agent and server
- they'd like to make the runtime (container) pluggable (runtime connector)

## Discussion

Kai proposes to move CUA on-top of ankaios, i.e. swap container management with
ankaios and reuse CUA/reimplement as a stand-alone component on top of it.

=> you get podman/podspec yamls for free

=> Ties you to systemd (same with bluechi), you can't swap for runit-init/sysvinit later which allow your to optimize aggressively.