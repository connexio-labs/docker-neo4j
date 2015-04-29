# neo4j

Neo4j is a highly scalable, robust (fully ACID) native graph database. Neo4j is used in mission-critical apps by thousands of leading, startups, enterprises, and governments around the world.

With the Dockerfile on repository you've a docker neo4j community edition image ready to go.

## Running

1. Execute this command:

    `docker run -it -p 7474:7474 connexiolabs/neo4j`

2. Access to http://localhost:7474 with your browser (or with boot2docker: `open "http://$(boot2docker ip):7474"`).

## Database Location

Ideally you're not leaving your data inside of a container. One option would be to mount a volume from your host and point the database location to it.

```sh
docker run \
  -it \
  -p 7474:7474 \
  -v $(pwd)/data:/var/lib/neo4j/data \
  connexiolabs/neo4j
```

Note: This will not work on boot2docker due to a [VirtualBox issue](http://stackoverflow.com/questions/18370043/neo4j-server-in-virtualbox-unable-to-create-rrd-store).
