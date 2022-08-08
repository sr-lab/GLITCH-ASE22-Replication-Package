# Replication Package - Automated Polyglot Security Smell Detection in Infrastructure as Code (ASE 2022)


This repository describes how to obtain and use the replication package for the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code", accepted at ASE 2022.[^1]

## What is the artifact?

The artifact includes the datasets for Ansible, Chef and Puppet containing 196,755 IaC scripts and 12,281,251 LOC that were used in the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code". It includes the code for the tool [GLITCH](https://github.com/sr-lab/GLITCH) with the version used for the experiments in the paper. It also includes the code for the dependency [puppetparser](https://github.com/Nfsaavedra/puppetparser) used by GLITCH. Finally, instructions to replicate the experiments in the paper are also provided in the artifact.

## Download

To obtain the replication package you should download it by accessing the link: https://figshare.com/s/d5283b1cdd1bcee38d85

When the download is concluded, you should have the file `glitch-latest.tar` (1.56GB, SHA1 ec21670e6e31cd6fd8c44de4b9a3f1bea398e79c).

The downloaded tar file is a **Docker image** that should be loaded with Docker to be used. To obtain more instructions on how to install and use the replication package please read the [INSTALL.md](INSTALL.md) file.

[^1]: Please note that the original title of this paper (as submitted to ASE) was "GLITCH: an Intermediate-Representation-Based Security Analysis for Infrastructure as Code Scripts". Following the reviewers' suggestion, we changed the title to better match our contributions.
