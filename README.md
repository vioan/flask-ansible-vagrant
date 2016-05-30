# flask-ansible-vagrant
Deploy a Flask application stack on a virtual machine with Ansible and Vagrant

## Components
The playbook builds an environment to run the application, consisting of several layers:

- Virtualenv
- Nginx
- Gunicorn

Note: PostgreSQL or any database is not installed and configured using this playbook

## Dependencies
To be able to run this project you need to install:

- Ansible
- Vagrant
- VirtualBox

## Usage

After installing the above dependencies on the host machine, you can edit the file **ansible/hosts** and **Vagrantfile** to change the ip address for the virtual machine - if you want, and then run/start the environment with **vagrant up**.

## Test it

In Browser: http://localhost:8080
