# Ansible
    Ansible Playbook collection to setup basic Linux tools, RVM, ElasticSearch, MongoDB

# Run Playbook
    ansible-playbook -i '52.8.118.29,' server.yml

# Server.yml
    Comment out the module that you do not want to run on the remote server.

# Check if mySql is installed
    dpkg --get-selections | grep mysql