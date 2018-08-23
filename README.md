# `elk-dcos` README

This repository contains Ansible playbooks that will install and configure
Filebeat and Logstash to send logs out to an external Elasticsearch cluster.

## Prerequisites

1. An installation of Elasticsearch. One possibility is to simply run Elasticsearch
on DC/OS with the following command:

    ```
    dcos package install elastic
    ```

1. For visualization, Kibana is one solution. One possibility is to simply run
Kibana on DC/OS with the following command:

    ```
    dcos package install kibana
    ```

1. Ansible needs to be installed on a system where the playbook will be executed
from.

1. SSH keys should be set up from the control node and all nodes that are being
managed.

## Usage

1. Create a copy of the example hosts file.

    ```
    cp hosts.example hosts
    ```

1. Populate the IP addresses for your DC/OS cluster nodes in the `hosts` file.

    ```ini
    [dcos-cluster]
    192.168.1.10
    192.168.1.11
    192.168.1.12
    ```

1. Run the playbook.

    ```
    ansible-playbook -i hosts --private-key <ssh_key> main.yaml
    ```
