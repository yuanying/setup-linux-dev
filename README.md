# README

    $ ansible-playbook -i hosts/local setup-vagrant.yml -e "@vars/local.yml" --connection=Local
    $ ansible-playbook -i hosts/test setup-vagrant.yml -e "@vars/test.yml"
    $ ansible-playbook -i hosts/production setup-vagrant.yml -e "@vars/production.yml"