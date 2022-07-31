# Replication Package Usage

## Installation

To be able to use the replication package follow the steps:

1. Install Docker by following the instructions for your operating system described [here](https://docs.docker.com/engine/install/).
2. Run ``docker load < glitch-latest.tar`` in the folder with the tar file previously downloaded.
3. Run ``docker run -it --name <NAME> -d glitch /bin/bash`` with <NAME> being any string.
4. Use the command ``docker ps -a`` to check the container ID of the container created in **point 3**. Copy the container ID.
5. Run ``docker attach <ID>`` with <ID> being the previously copied container ID.
6. The docker container is ready to use!

It is important to mention that this instructions present tested with a **Linux system**. For other operating systems, some adjustments may need to be made.

## Usage

On the root folder ``\`` a file called ``README`` describes the necessary folder structure to replicate the results. 
The tool ``GLITCH`` and its dependency ``puppetparser`` are already installed in the docker image. 
The folder ``RESULTS`` contains the file ``README.md`` with instructions to replicate the experiments of the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code".
This folder also contains the datasets and the final outputs of our experiments.
