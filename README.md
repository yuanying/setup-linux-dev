# README

1. Setup development environment
2. Setup server

## Setup development environment

Setup local development environment

    $ sudo apt-get update && sudo apt-get install -y python-pip
    $ sudo pip install ansible
    $ ansible-playbook -i hosts/local setup-devenv.yml \
                       -e "@vars/local.yml" --connection=local

### Example of vars/local.yml

    ---
    localhost: true
    proxy:
      http_proxy: http://proxy.host:8080
      https_proxy: http://proxy.host:8080

## Setup server

### Test

    $ vagrant up
    $ ansible-playbook -i hosts/test setup-server.yml -e "@vars/test.yml"
    $ ansible-playbook -i hosts/test setup-server-without-monitor.yml -e "@vars/test.yml"

### Setup production environment

    $ # Write hosts/production
    $ # Write vars/production.yml
    $ ansible-playbook -i hosts/production setup-server.yml \
                       -e "@vars/production.yml"
