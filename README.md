# clockwork_bcftools_docker
Dockerised bcftools for Clockwork using CI/CD to Oracle Container Registry

## Creating a new release

When there is a new release of bcftools at https://github.com/samtools/bcftools, 
you will need to do the following steps to make it available to the GPAS-TB-Workflow

* Update the `Dockerfile` in `environments` to set the release you want, normally
this will be the latest, but don't use the `latest` tag, use the version number tag.
Update both the version in the `LABEL` section and the `ENV` version.
* Create a PR, have it reviewed, and merge to the `main` branch
* Create a release using the same version number tag you used in the `Dockerfile` 
but with the format of `v#.#.#` this is important otherwise the actions with not 
pick up the release and run
    - The GitHub actions will build the docker container image and push it to the OCR
    (Oracle Container Registry)
