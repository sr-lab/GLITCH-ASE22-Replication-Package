# Replication Package Usage

## Installation

To be able to use the replication package follow the steps:

1. Install Docker by following the instructions for your operating system described [here](https://docs.docker.com/engine/install/).
2. Run ``docker load < glitch-latest.tar`` in the folder with the tar file previously downloaded.
3. Run ``docker run -it --name glitch-replication-package -d glitch /bin/bash``
5. Run ``docker attach glitch-replication-package``
6. The docker container is ready to use!

It is important to mention that these instructions were tested with a **Linux Ubuntu system**. For other operating systems, some adjustments may need to be made.

## Usage

On the root folder ``/`` a file called ``README`` describes the container's folder structure.
The tool ``GLITCH`` and its dependency ``puppetparser`` are already installed in the docker image. 
The folder ``RESULTS`` contains the file ``README.md`` with instructions to replicate the experiments of the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code".
This folder also contains the datasets and the final outputs of our experiments.

To test GLITCH run:
``
python3 -m glitch --tech puppet /RESULTS/puppet/repos/github/camptocamp@puppet-python/manifests/pip.pp
``
You should get the following output:
```
/RESULTS/puppet/repos/github/camptocamp@puppet-python/manifests/pip.pp
Issue on line 4: Switch statement should have default condition
$pip_package = $::osfamily ? {
```
