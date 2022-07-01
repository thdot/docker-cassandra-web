## [hub.docker.com/thdot/cassandra-web](https://hub.docker.com/r/thdot/cassandra-web)

A simple/small/Alpine based Docker image built from [cassandra-web](https://github.com/avalanche123/cassandra-web) web UI.

## [Tags](https://hub.docker.com/r/thdot/cassandra-web)
- `latest`, `0.5.0`

## Quick Start

The container uses environment variables for configuration. Following parameters are available:

*  CASSANDRA_HOST_IPS
   *  A list of Cassandra nodes in the cluster
   *  *Note*: Currently, [only IPs and no FQDNs are accepted](https://github.com/avalanche123/cassandra-web/issues/19)
   *  Default: 127.0.0.1
*  CASSANDRA_PORT
   *  Port exposed by the nodes
   *  Default: 9042
*  CASSANDRA_USERNAME
   *  Default: cassandra
*  CASSANDRA_PASSWORD
   *  Default: cassandra
*  CASSANDRA_WEB_BIND
   * ip:port or path for cassandra web to bind on
   * Default: 0.0.0.0:3000

### Docker CLI

```bash
docker run -d -p 3000:3000 \
    -e CASSANDRA_HOST_IPS=127.0.0.1 \
    -e CASSANDRA_PORT=9042 \
    -e CASSANDRA_USERNAME=cassandra \
    -e CASSANDRA_PASSWORD=cassandra \
	thdot/cassandra-web
```


### Docker Compose

Provided with the repo. Since *cassandra-web* only works with IP address, docker-compose creates network accordingly and gives *cassandra* container a static IP address, which is used on *cassandra-web* configuration.

You can tryout Web UI by just `docker-compose up -d`.

## Credits

It is derived from the [image of Doğukan Çağatay](https://hub.docker.com/r/dcagatay/cassandra-web), which
itself is based on an [image from MG Cloud Consultants](https://hub.docker.com/r/markusgulden/cassandra-web).
