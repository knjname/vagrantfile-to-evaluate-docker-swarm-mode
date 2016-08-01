
# Vagrant file for launching manager/worker machines described in Docker swarm mode tutorial

This file is to launch the following VMs described in https://docs.docker.com/engine/swarm/swarm-tutorial/ by running `vagrant up`. You can test and evaluate docker swarm mode which has been introduced since Docker 1.12.

1. manager1
   * 192.168.99.100
   * `vagrant ssh manager1`
2. worker1
   * 192.168.99.101
   * `vagrant ssh worker1`
3. worker2
   * 192.168.99.102
   * `vagrant ssh worker2`

All the above machines will run initialization commands on its beginning to install docker >= 1.12.

