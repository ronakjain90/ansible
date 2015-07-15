# Ansible
    Ansible Playbook collection to setup basic Linux tools, RVM, ElasticSearch, MongoDB

# Run Playbook
    ansible-playbook -i '52.8.210.41,' server.yml -- Working
    ansible-playbook -i '52.8.196.248,' server.yml -- working


# Server.yml
    Comment out the module that you do not want to run on the remote server.

# Check if mySql is installed
    # https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu
    # dpkg --get-selections | grep mysql

# check if php is installed

    # default folder /var/www/html/
    # create a file index.php with
    # <?php phpinfo() ; ?>
    # open IPaddress/index.php to check if php is installed

# to install php admin

    # sudo mysql_install_db
    # sudo /usr/bin/mysql_secure_installation
    # https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu
