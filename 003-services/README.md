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
