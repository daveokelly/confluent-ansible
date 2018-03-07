# Introduction 

Ansible playbooks for installing the [Confluent Platform](http://www.confluent.io).

## Example hosts.yml

```yaml
all:
  vars:
    ansible_connection: ssh
    ansible_ssh_user: centos
    ansible_become: True
zookeeper:
  hosts:
    zookeeper-01.example.com:
    zookeeper-02.example.com:
    zookeeper-03.example.com:
broker:
  hosts:
    broker-01.example.com:
      kafka:
        broker:
          id: 1
    broker-02.example.com:
      kafka:
        broker:
          id: 2
    broker-03.example.com:
      kafka:
        broker:
          id: 3
connect-distributed:
  hosts:
    connect-01.example.com:
    connect-02.example.com:
schema-registry:
  hosts:
    connect-01.example.com:
    connect-02.example.com:
control-center:
  hosts:
    control-center.example.com:
```

## Running

```bash
ansible-playbook -i hosts.yml all.yaml
```