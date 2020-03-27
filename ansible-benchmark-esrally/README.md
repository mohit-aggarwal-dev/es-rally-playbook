Ansible Benchmark Esrally
=========

Execute esrally to benchmark Elasticsearch and get the results in json-format.

Requirements
------------

Download my custom filters from [the Github repository](https://github.com/SamyCoenen/ansible-filters).

Role Variables
--------------

    track: geonames
    challenge: append-no-conflicts
    git_folder: /tmp/esrally
    config.version: 8
    env.name: rally
    root.dir: /home/es/.rally/benchmarks
    java8.home: /usr/lib/jvm/java-8-openjdk-amd64
    local.dataset.cache: ${node:root.dir}/data
    datastore.type: elasticsearch
    datastore.host: localhost
    datastore.port: 9200
    datastore.secure: False
    datastore.user: elastic
    datastore.password: changeme
    default.track.url: https://github.com/elastic/rally-tracks
    preserve_benchmark_candidate: True
    cluster_health: yellowl.

Dependencies
------------

- geerlingguy.java
- samycoenen.ansible-role-esrally

Example Playbook
----------------


    - hosts: servers
      vars:
        datastore_host: elasticsearch.example.com
      roles:
         - samycoenen.ansible-benchmark-esrally

License
-------

EUPL v1.2

Author Information
------------------

This role was created in 2017 by [Samy Coenen](https://www.samycoenen.be/).
