# Compose - Authentication stack

## Description

Compose cookbook to deploy an authentication stack with these components:

* [Keycloak](https://www.keycloak.org/) - IAM ([official Docker image](https://hub.docker.com/r/jboss/keycloak/))
* [OpenLDAP](https://www.openldap.org/) - Internal LDAP ([Osixia Docker image](https://hub.docker.com/r/osixia/openldap))
* [Postgres](https://www.postgresql.org/) - Database to persist IAM data ([official Docker image](https://hub.docker.com/_/postgres))
* [PHP LDAP admin](http://phpldapadmin.sourceforge.net/) - LDAP viewer ([Osixia Docker image](https://hub.docker.com/r/osixia/phpldapadmin))
* [Keycloak gatekeeper](https://github.com/keycloak/keycloak-gatekeeper) - IAM proxy ([official Docker image](https://hub.docker.com/r/keycloak/keycloak-gatekeeper))


## Monitoring

Monitoring is exposed by [Prometheus](https://prometheus.io/) exporters.

* [Postgres exporter](https://hub.docker.com/r/wrouesnel/postgres_exporter)


## Backup

It can be done using a dedicated worker.


## Usage

Docker-compose files:

* `docker-compose.yml`: Base of deployment
* `docker-compose.gatekeeper.yml`: Protect PHP LDAP admin behind Keycloak
* `docker-compose.backup.yml`: Used to manage a backup container
* `docker-compose.override.yml`: Add some alias to be used with Traefik
