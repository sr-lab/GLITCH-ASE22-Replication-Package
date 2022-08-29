# Replication Package - Automated Polyglot Security Smell Detection in Infrastructure as Code (ASE 2022)

This repository describes how to obtain and use the replication package for the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code", accepted at ASE 2022.

## What is the artifact?

The artifact includes the datasets for Ansible, Chef and Puppet containing 196,755 IaC scripts and 12,281,251 LOC that were used in the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code". It includes the code for the tool [GLITCH](https://github.com/sr-lab/GLITCH) with the version used for the experiments in the paper. It also includes the code for the dependency [puppetparser](https://github.com/Nfsaavedra/puppetparser) used by GLITCH. Finally, instructions to replicate the experiments in the paper are also provided in the artifact.

## Download

To obtain the replication package you should download it by accessing the link: 
https://doi.org/10.6084/m9.figshare.19726603.v2

When the download is concluded, you should have the file `glitch-latest.tar` (1.7GB, SHA1 3d97ad9c3e39feb42a0ba065049aba907002b185, MD5 d9de60550dc558ad227ab14ceef64654).

The downloaded tar file is a **Docker image** that should be loaded with Docker to be used. To obtain more instructions on how to install and use the replication package please read the [INSTALL.md](INSTALL.md) file.
