# KN03 screenshots + description

## A) Understanding Cloud-init files:

### YAML-file:

```yaml
#cloud-config # Comment
users: # Keyword to configure a user
  - name: ubuntu # Name of the user
    sudo: ALL=(ALL) NOPASSWD:ALL # gives the user right to use sudo commands without inputing the password
    groups: users, admin # assigned the user to the listed groups
    home: /home/ubuntu # Assignes the listed folder as the homeo folder of the user
    shell: /bin/bash # asignes the listed shell as the shell of the user
    ssh_authorized_keys: # SSH-Key with which you can log into the user
      - ssh-rsa MIIEogIBAAKCAQEAgq+fgQSlXmgZgVt13b1t7opDsZMlry5ZmP1vUMCuz2vwC5QUcOFtq38jmvgcbikmbFcCymkCn3NHaSr3tthz6rrkgAu73wEUqKWQl8k3LrMjcPx6FLkp2Q/YEZe82lTjmflqTNHZVD+LqWsDzB4HjUclxUQ084vmeQf1wHPGFxschCsUL8+nRCfrwWuqS8+WUfrR+IW8ph6c6+ct5+kvc7DnI9Du/mGyXmp1DUWXesRDU1nPb/f3TgPjSh04MlHCGB9Q3NN1n7MDJK8KhGS41mygWyp7awG8Ki4Zo5TxGG6Irly7xViBiLzTnF0Bkq4R7K/59kJj+wNNYUWYn5wAbwIDAQABAoIBAG1Y7alSbdwUVmL6WCD1Q2p4njOS39E4gxeT1vRGhP5hXjUR7hiVRuJcOzqLp541KEU2eMtMGjm4h2Pj4+lGK5eYUWEicEwj51lFTzrxzg5xLZJ4bt2wIOfSbgQqZoZ4yQgovV0RqTrpAL79H+xGpCL+CQiKDZRK1skmc+ZX+MOTYaSMViMHZGNFIkVwYf0T4i+QGaW4k6EIbTTlAt/o0QP3g2zyzITSsOYnTq/NOE32X24VuGwSpdhQ1fusTpZDePEWVjO0V4RcnGbM38WkAbpnxjCjMOJ759Z2AbL6aSVN7qmgWI3DZVhl8w+noHMZkvY4kvibP+JliDmxiCJr5UECgYEA1x53HUmN0B7YXsgKni6T9DY9JrqaU1QsCRcWZgMy+eGvSWuiz/XUhfgCbXLLpS1xYRui0bmpgTfTtj+yVKs7O/xvzQaUcYcqUpiK4YD0o6b1gV2rSknAKQKa32o65nTDXDA/AFwoXS7IONo0z4Tdm/vwgiekiPcNQoyxcwtsRBkCgYEAm4V+zlyHwhG2+l9OrMb9ASkxrxlO9JnXeKLQtQwT5EeDiHKg2Lpi6Ay7xy7I3JtZboMiF7dpn295XeOfCMnpgUAVlvMMTSnTScTsKfkE0rH4TddNZnkrRHOuYOSb9bBHHpBiQUYjL75P51BTx6M25VmCrdM3/MBfr9FNdSrFuccCgYBJqRPugmY98qHyaptAKQDeqcfswA7iI7tkbXRtAAFvkTj9cg7xGONp8E+cfKeA6vuc3eK139ZL+frTuCHvXibNVpZN5UflS/xRBgzgRNEATMZaQuHJcVGMeWjgwbZjfW373kVkcSodJkzHMujMelmL9QwY9Uwg3j+7HwQQOcQb2QKBgAtzK5/TzibqmPcb9zXfPJdOShsjGN4HSYbXLdh2eCxxW2y7S75JEqkU7uo+NomPYmkxfFwUo9EaKuxPqtDB1NAwQKapZDl2H9kph12buNAuTCKm/ErUFuxmO+tkSVswTDwi0ykNGeAU+dsE3fYvvQXrriRQDaotG55dIX/D02TXAoGAKxH1wYfgCWLoxOplbOYsJzZrMf3NX+ZLmW48SawHi+CjrsIVycyJPBL4xydX1eU3w2k+IVKFPnQGiuup725AuwQNRyoySsdIds0eiRwbl/5xZtPRqBbA4dgVQWJdtfQUXAAcNJ8sONOK8qYCPY4bZXsVYvlK2UfIfXsHcL8QfJo= aws-key       
ssh_pwauth: false # Deaklivates SSH-password-login
disable_root: false # Forbids the user to take away the root acces
package_update: true # Allows the user to install packages
packages: # installs the packages listed below
  - curl 
  - wget 
```

## B) SSH-Key and Cloud-init:

```yaml
#cloud-config # Comment
users: # Keyword to configure a user
  - name: ubuntu # Name of the user
    sudo: ALL=(ALL) NOPASSWD:ALL # gives the user right to use sudo commands without inputing the password
    groups: users, admin # assigned the user to the listed groups
    home: /home/ubuntu # Assignes the listed folder as the homeo folder of the user
    shell: /bin/bash # asignes the listed shell as the shell of the user
    ssh_authorized_keys: # SSH-Key with which you can log into the user
        # my private key
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCCr5+BBKVeaBmBW3XdvW3uikOxkyWvLlmY/W9QwK7Pa/ALlBRw4W2rfyOa+BxuKSZsVwLKaQKfc0dpKve22HPquuSAC7vfARSopZCXyTcusyNw/HoUuSnZD9gRl7zaVOOZ+WpM0dlUP4upawPMHgeNRyXFRDTzi+Z5B/XAc8YXGxyEKxQvz6dEJ+vBa6pLz5ZR+tH4hbymHpzr5y3n6S9zsOcj0O7+YbJeanUNRZd6xENTWc9v9/dOA+NKHTgyUcIYH1Dc03WfswMkrwqEZLjWbKBbKntrAbwqLhmjlPEYboiuXLvFWIGIvNOcXQGSrhHsr/n2QmP7A01hRZifnABv aws-key       
        # teacher's private key
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC0WGP1EZykEtv5YGC9nMiPFW3U3DmZNzKFO5nEu6uozEHh4jLZzPNHSrfFTuQ2GnRDSt+XbOtTLdcj26+iPNiFoFha42aCIzYjt6V8Z+SQ9pzF4jPPzxwXfDdkEWylgoNnZ+4MG1lNFqa8aO7F62tX0Yj5khjC0Bs7Mb2cHLx1XZaxJV6qSaulDuBbLYe8QUZXkMc7wmob3PM0kflfolR3LE7LResIHWa4j4FL6r5cQmFlDU2BDPpKMFMGUfRSFiUtaWBNXFOWHQBC2+uKmuMPYP4vJC9sBgqMvPN/X2KyemqdMvdKXnCfrzadHuSSJYEzD64Cve5Zl9yVvY4AqyBD aws-key
    ssh_pwauth: false # Deaklivates SSH-password-login
disable_root: false # Forbids the user to take away the root acces
package_update: true # Allows the user to install packages
packages: # installs the packages listed below
  - curl 
  - wget 
```

### Instance-list screenshot:
<picture>
  <img src="">
</picture>

### Resault of using the ***first*** SSH-Key:
<picture>
  <img src="">
</picture>

### Resault of using the ***second*** SSH-Key:
<picture>
  <img src="">
</picture>

### Excerpt from the cloud-init log:
<picture>
  <img src="">
</picture>

## C) Template:

### Adjusted YAML-file:
```yaml
#cloud-config # Comment
users:
  - name: ubuntu
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: users, admin
    home: /home/ubuntu
    shell: /bin/bash
    ssh_authorized_keys: # SSH-Key with which you can log into the user
        # my private key
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCCr5+BBKVeaBmBW3XdvW3uikOxkyWvLlmY/W9QwK7Pa/ALlBRw4W2rfyOa+BxuKSZsVwLKaQKfc0dpKve22HPquuSAC7vfARSopZCXyTcusyNw/HoUuSnZD9gRl7zaVOOZ+WpM0dlUP4upawPMHgeNRyXFRDTzi+Z5B/XAc8YXGxyEKxQvz6dEJ+vBa6pLz5ZR+tH4hbymHpzr5y3n6S9zsOcj0O7+YbJeanUNRZd6xENTWc9v9/dOA+NKHTgyUcIYH1Dc03WfswMkrwqEZLjWbKBbKntrAbwqLhmjlPEYboiuXLvFWIGIvNOcXQGSrhHsr/n2QmP7A01hRZifnABv aws-key       
        # teacher's private key
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC0WGP1EZykEtv5YGC9nMiPFW3U3DmZNzKFO5nEu6uozEHh4jLZzPNHSrfFTuQ2GnRDSt+XbOtTLdcj26+iPNiFoFha42aCIzYjt6V8Z+SQ9pzF4jPPzxwXfDdkEWylgoNnZ+4MG1lNFqa8aO7F62tX0Yj5khjC0Bs7Mb2cHLx1XZaxJV6qSaulDuBbLYe8QUZXkMc7wmob3PM0kflfolR3LE7LResIHWa4j4FL6r5cQmFlDU2BDPpKMFMGUfRSFiUtaWBNXFOWHQBC2+uKmuMPYP4vJC9sBgqMvPN/X2KyemqdMvdKXnCfrzadHuSSJYEzD64Cve5Zl9yVvY4AqyBD aws-key
ssh_pwauth: false # Deaklivates SSH-password-login
disable_root: false # Forbids the user to take away the root acces
package_update: true # Allows the user to install packages
packages: # installs the packages listed below
  - curl 
  - wget 
  - apache2
  - php
  - libapache2-mod-php
  - mariadb-server
  - php-mysqli
  - adminer
write_files:
  - path: /var/www/html/info.php
    content: |
        <?php

        // Show all information, defaults to INFO_ALL
        phpinfo();

        ?>
    permissions: '0644'
  - path: /var/www/html/db.php
    content: |
        <?php
            //database
            $servername = "127.0.0.1";
            $username = "admin";
            $password = "password";
            $dbname = "mysql";

            // Create connection
            $conn = new mysqli($servername, $username, $password, $dbname);
            // Check connection
            if ($conn->connect_error) {
                    die("Connection failed: " . $conn->connect_error);
            }

            $sql = "select Host, User from mysql.user;";
            $result = $conn->query($sql);
            while($row = $result->fetch_assoc()){
                    echo($row["Host"] . " / " . $row["User"] . "<br />");
            }
            //var_dump($result);
        ?>
    permissions: '0644'
runcmd:
  - sudo a2enconf adminer
  - sudo systemctl restart apache2
```

## D) Splitting the Web and the Database servers

### Connection with the admin user:
<picture>
  <img src="">
</picture>
