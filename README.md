# Ansible
    Ansible Playbook collection to:

    1. Setup Apache
    2. Clone Remote github Repositories
    3. Setup ElasticSearch
    4. Setup Erlang/Elixir
    5. Setup NodeJS
    6. Setup Phoenix
    7. Setup PhP
    8. Setup Redis
    9. Setup RVM
    10. Add SSH Keys
    11. Setup Mongodb
    12. Setup MySQL
    13. Setup Nginx as a reverse proxy for multiple sites with SSL

# Run Playbook
    Run this command to run the playbook:

    `ansible-playbook -i inventory main.yml`

    Place your `inventory` file in the directory you wish to your ansible commands in the following format

    ```
    [remote_server]
    your_ip_address_here ansible-connection=ssh ansible_ssh_user=username ansible_ssh_pash=password

    [remote_server:vars]
    yourvariables=variable-content
    ```

    And setup your `main.yml` to include the roles you want:

    ```
    ---

    - hosts: remote_server
      gather_facts: yes
      become: yes

      vars:
        NODEJS_VERSION: "12"
        ansible_distribution_release: "xenial"
        nginx_revproxy_sites:
          test.acuments.com: {appname: 'test', port: 5000, socket: true}
          test1.acuments.com: {appname: 'test1', port: 3000, socket: false}
          test2.acuments.com: {appname: 'test2', port: 4004, socket: false}

      roles:
        - ansible-apache
        - ansible-clone-repo
        - ansible elasticsearch
        - ansible-mongodb
        - ansible-phoenix
        - ansible-php
        - ansible-redis
        - ansible-rvm
        - ansible-ssh
        - ansible-nodejs
        - ansible-erlang-elixir
        - ansible-phoenix
        - ansible-mysql
        - ansible-nginx
    ```

    Add/Remove sites from the `nginx_revproxy_sites` variable specifed in the main.yml. Specify `socket: true `if your site is using socket connections.