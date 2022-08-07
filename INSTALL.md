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

To test GLITCH run:
``
glitch --tech puppet --smells security /RESULTS/puppet/repos/github/camptocamp@puppet-python/manifests/pip.pp
``
You should get the following output:
```
/RESULTS/puppet/repos/github/camptocamp@puppet-python/manifests/pip.pp
Issue on line 4: Missing default case statement - Not handling every possible input combination might allow an attacker to trigger an error for an unhandled value. (CWE-478)
$pip_package = $::osfamily ? {

+--------------------------------+-------------+----------------------------+---------------------------+
|                          Smell | Occurrences | Smell density (Smell/KLoC) | Proportion of scripts (%) |
+--------------------------------+-------------+----------------------------+---------------------------+
|               Admin by default | 0           | 0.0                        | 0.0                       |
|                 Empty password | 0           | 0.0                        | 0.0                       |
|            Hard-coded password | 0           | 0.0                        | 0.0                       |
|              Hard-coded secret | 0           | 0.0                        | 0.0                       |
|                Hard-coded user | 0           | 0.0                        | 0.0                       |
|     Invalid IP address binding | 0           | 0.0                        | 0.0                       |
| Missing default case statement | 1           | 41.67                      | 100.0                     |
|             No integrity check | 0           | 0.0                        | 0.0                       |
|             Suspicious comment | 0           | 0.0                        | 0.0                       |
|        Use of HTTP without TLS | 0           | 0.0                        | 0.0                       |
|          Weak Crypto Algorithm | 0           | 0.0                        | 0.0                       |
| ------------------------------ | ----------- | -------------------------- | ------------------------- |
|                       Combined | 1           | 41.67                      | 100.0                     |
+--------------------------------+-------------+----------------------------+---------------------------+
+-----------------+---------------+
| Total IaC files | Lines of Code |
+-----------------+---------------+
|        1        |       24      |
+-----------------+---------------+
```

## Replication
This section describes how to replicate the experiments of the paper "GLITCH: Automated Polyglot Security Smell Detection in Infrastructure as Code" on the Docker image provided.

The folder ``RESULTS`` contains the file ``README.md`` with the same instructions described here. This folder also contains the datasets and the final outputs of our experiments.

### Ansible

#### Oracle Dataset

To obtain the results of precision and recall for the Ansible oracle dataset (Table 7), run the following commands:

```
cd /RESULTS/ansible/oracle-dataset-analysis
./oracle-results.sh
```

The output obtained by running SLAC and both configurations of GLITCH on the oracle dataset is already provided on the folder `ansible/oracle-dataset-analysis`. If you only want to check the final results run the following commands:

```
cd /RESULTS/ansible/oracle-dataset-analysis
python3 calculate-metrics.py SLAC-ansible-oracle.csv
python3 calculate-metrics.py GLITCH-SLAC-ansible-oracle.csv
python3 calculate-metrics.py GLITCH-ansible-oracle.csv
```

#### IaC Dataset

To obtain the results of occurrences, smell density and proportion of scripts for the Ansible IaC dataset (Table 10, 11 and 12), run the following commands (**NOTE:** the execution will take a while &ndash; ~40 minutes in our experiments):

```
cd /RESULTS/ansible/iac-dataset-analysis
./results.sh
```

The output obtained by running SLAC and GLITCH on the IaC dataset is already provided on the folder `ansible/iac-dataset-analysis`. If you only want to check the final results run the following commands:

```
cd /RESULTS/ansible/iac-dataset-analysis
python3 ../../dump-dataset-stats.py --tool slac-ansible ../repos SLAC-ansible.csv .yaml,.yml
python3 ../../dump-dataset-stats.py --tool glitch ../repos GLITCH-ansible.csv .yaml,.yml
```
