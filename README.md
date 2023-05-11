# ansible-docker-test

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
dry run:
```
ansible-playbook --ask-pass --ask-become-pass --inventory inventory.yml --check --diff playbook.yml
```

run:
```
ansible-playbook --ask-pass --ask-become-pass --inventory inventory.yml playbook.yml
```
