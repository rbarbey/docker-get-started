Part 3: Services

Talks about the second level of distributed application hierarchy, services (called containers in production). Achieved via `docker-compose.yml` file which configures a service and scaling of containers.

* pull image from the registry
* run configured number of instances (`replicas`) of that image as a service called `web`
* each instance is limited in resources:
 * 10% of CPU across cores
 * 50 MB of RAM
* restart containers if they fail
* map port `4000` on the host to port `80` inside the container
* instruct containers to share port `80` via a load-balanced network called `webnet`
* define `webnet` network with default settings

## Docker Swarm
Turn this node into a swarm manager:
```bash
docker swarm init
```

Deploy services with `getstartedlab` as name:
```bash
docker stack deploy -c docker-compose.yml getstartedlab
```

Take down the app and the swarm:
```bash
docker stack rm getstartedlab
docker swarm leave --force
```

## Command cheat sheet
```bash
docker stack ls                                            # List stacks or apps
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker service ls                 # List running services associated with an app
docker service ps <service>                  # List tasks associated with an app
docker inspect <task or container>                   # Inspect task or container
docker container ls -q                                      # List container IDs
docker stack rm <appname>                             # Tear down an application
docker swarm leave --force      # Take down a single node swarm from the manager
```
