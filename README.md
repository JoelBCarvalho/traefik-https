# Traefik HTTPS for local tests using ACME Testing environment

## Objectives

We wanted a simple local VM to clone our remote cloud instances.
 
Use traefik as a reverse proxy in a docker stack. 

To secure the connection, we used a simulated Let's Encrypt container based stack named boulder.
https://github.com/containous/traefik/tree/master/examples/acme

This provides Traefik-boulder full stack environment.
This environment may be used in order to quickly test developments on ACME certificates management.

The provided Boulder stack is based on the environment used during integration tests.

I've also added a whoami service app and a nginx server for routing requests.

## Start Vagrant
```bash
$ sudo vagrant up
```

Note: Use sudo to open up port 80. Without it, vagrant by default does not port forward port 80 to host.

```bash
$ sudo vagrant ssh
```
Note: If vagrant requires password, use *vagrant*
## Deploy

Deploy the complete setup on a Docker host.

```bash
$ docker-compose up
```

## Directory content

* **docker-compose.yml** : Docker-Compose file which contains the description of Traefik and all the boulder stack containers to get,
* **traefik.toml** : Traefik configuration file used by the Traefik container described above,

