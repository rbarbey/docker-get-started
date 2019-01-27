# Get Started, Part 2: Containers

This part of the tutorial talks about the fundamental concepts of Docker, e.g. what's the difference between an image and a container. The `Dockerfile` builds an image which contains a very simple web service written in Python. To build this image, call

```bash
docker build -t friendlyhello .
```

To spin up a container based on the image, call

```bash
docker run -d -p 4000:80 friendlyhello
```

Tags are another concept in Docker. When the image was first built, it was tagged with `friendlyhello` which in this case is a name for the image. But it's also possible to tag an image, like so

```bash
docker tag friendlyhello rbarbey/get-started:part2
```

where `rbarbey/get-started:part2` consists of three parts:
* `rbarbey` is the username (referring to a Docker registry)
*  `get-started` is the repository
* `part2` is the tag

Coming from other artifact repository like Maven Central, this was at first a bit confusing to me. I would find it more intuitive if the username makes up a repository (in the public Docker Hub, for example) and inside that repository there are all your images, like `get-started` in this case.
