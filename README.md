# README

    $ ansible-playbook -i hosts/test setup-vagrant.yml -e "@vars/test.yml"
    $ ansible-playbook -i hosts/production setup-vagrant.yml -e "@vars/production.yml"

If you use this script on local:

    $ sudo apt-get update && sudo apt-get install -y python-pip
    $ sudo pip install ansible
    $ ansible-playbook -i hosts/local setup-vagrant.yml -e "@vars/local.yml" --connection=Local

## Example of loca.yml

    ---
    http_proxy: http://proxy.host:8080
    https_proxy: http://proxy.host:8080