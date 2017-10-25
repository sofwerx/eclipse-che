# eclipse-che

This is a management harness for an eclipse-che environment.

# Usage:

Install `docker` and `docker-compose` for your development workstation following the Docker documentation.

- https://docs.docker.com/engine/installation/
- https://docs.docker.com/compose/install/

Clone this repo and run `docker-compose up` in the repo directory to start using che:

    git clone https://github.com/sofwerx/eclipse-che
    cd eclipse-che
    docker-compose up

You can use `cntl+C` to stop that che starter container once you know there are no errors running it.

To run the che starter container in the background, just use:

    docker-compose up -d

This will also automagically restart when you reboot your computer.

The che web service should be listening on your docker-engine host on port 8080.

You can now interact with Che by clicking on the following URL:

- http://localhost:8080

# Further reading

https://www.eclipse.org/che/docs/setup/getting-started/
