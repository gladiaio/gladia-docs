# Release Process

You can follow the project advancements here : [https://github.com/gladiaio/gladia/projects/1](https://github.com/gladiaio/gladia/projects/1)

Each merge into the 'main' branch will generate a release that has been full tested and available here : [https://hub.docker.com/repository/docker/gladiaio/gladia](https://hub.docker.com/repository/docker/gladiaio/gladia)

We use [CDS](https://github.com/ovh/cds) to perform all our CI/CD process.

Each push on github is built, unit tested and release if the test passes on main branch.

Each pull request needs to pass checks to be merged.
