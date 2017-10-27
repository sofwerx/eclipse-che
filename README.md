# eclipse-che

This is a management harness for a docker based [eclipse-che](https://www.eclipse.org/che/) environment.

# Docker:

Install `docker` and `docker-compose` for your development workstation following the Docker documentation.

- https://docs.docker.com/engine/installation/
- https://docs.docker.com/compose/install/

`docker-engine` is the thing running inside a linux host OS.

- On Windows, you need hyper-v to run a Linux VM, which does not come with Home Edition.
- On Mac, it will use xhyve which is built-in and free.
- On Linux, it will install a `docker-engine` natively on your linux host OS, so no VM will be required.

`docker-compose` is a command-line tool for managing a group of containers with a `docker-compose.yml` file in your projects.

# Usage:

Clone this repo and run `docker-compose up` in the repo directory to start using che:

    git clone https://github.com/sofwerx/eclipse-che
    cd eclipse-che

To spin up the Che launcher container, run this:

    docker-compose up

You can use `cntl+C` to stop that che starter container once you know there are no errors running it.

To run the che starter container in the background, just add the `-d` argument to `up`:

    docker-compose up -d

This will also automagically restart when you reboot your computer.

The che web service should be listening on your docker-engine host on port 8080.

You should now be able to interact with Che by clicking on the following URL:

- http://localhost:8080

# Windows Note:

Linux and Mac docker-engines use the standard unix domain socket path of `/var/run/docker.sock`

Linux and Mac docker and docker-compose also presume the default:

    DOCKER_HOST=unix:///var/run/docker.sock

Windows is different.

The `/var/run/docker.sock` path does not exist on windows. Because of that, there is a `.env` file here that defines:

    COMPOSE_CONVERT_WINDOWS_PATHS=1

Documentation suggests that should prevent Windows from erroring out, but I've not yet been able to verify this.

On Windows, you may also need to define:

    DOCKER_HOST=npipe:////./pipe/docker_engine

Please let Ian know if you run into problems here.

# Further reading

https://www.eclipse.org/che/docs/setup/getting-started/
