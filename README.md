# ansible-docker-test

This project demonstrates how to use ansible between 2 docker containers.

The first docker container (control-node) acts as the ansible control node and the other docker container (managed-node) is the managed node which is controlled by ansible.

## start docker containers
```
docker compose up
```

## test ssh login from control-node to managed-node
login into control-node:
```
docker compose exec control-node bash
```

ssh into managed-node once so that this host's fingerprint is added to known_hosts (password: root)
```
ssh root@managed-node
```

after that you can exit managed-node.

## run ansible playbook from control-node
login into control-node:
```
docker compose exec control-node bash
```

dry run:
```
ansible-playbook --ask-pass --ask-become-pass --inventory inventory.yml --check --diff playbook.yml
```

run:
```
ansible-playbook --ask-pass --ask-become-pass --inventory inventory.yml playbook.yml
```
