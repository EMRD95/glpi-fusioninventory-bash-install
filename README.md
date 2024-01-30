# glpi-fusioninventory-bash-install with Nginx

 <img alt="GLPI IMG" src="https://glpi-project.org/wp-content/uploads/2022/01/assets-2.png">

## About this script

This script was written in order to quickly install the latest version of GLPI (currently 10.0.6) and FusionInventory (10.0.6+1.1) on Ubuntu & Debian servers.

The script will install, Apache, MariaDB, PHP and dependencies, and download and install GLPI and Fusion Inventory from their Official GLPI repo and configure the database for you.
Once the script is executed, the only thing you have to do will be to connect to GLPI.

The installation of GLPI is done without SSL. If you need to open access to GLPI from the outside and/or an SSL certificate, I recommend that you use a reverse proxy.

⚠️ It is strongly recommended to run this script on a fresh install.

### Default accounts
| Login | Password | Role |
|--|--|--|
glpi|glpi|admin account
tech|tech|technical account
normal|normal|"normal" account
post-only|postonly|post-only account

### Read the documentation
Know that I have no connection with the team that develops GLPI and/or FusionInventory
If you encounter a problem with this script on one of the compatible distributions, you can create an issue, i will help you with pleasure.
If you encounter a problem with GLPI and/or FusionInventory and you need more information on how they works, I recommend that you read the documentations:

[GLPI Administrators Docs](https://glpi-install.readthedocs.io/)

[GLPI Users Docs](https://glpi-user-documentation.readthedocs.io/)

[FusionInventory Docs](https://documentation.fusioninventory.org/)

## Compatibility
Since this script uses apt, it currently only works on debian-based distributions.
This script was tested on this distributions:
| OS | VERSION| COMPATIBILITY|
|--|--|--|
|Debian|10|⚠️ Never tried, if you choose to force the script, it is at your own risk. |
|Debian|11|✅|
|Ubuntu|22.04|✅|
|Ubuntu|22.10|⚠️ Never tried, if you choose to force the script, it is at your own risk.|


## How to use
GLPI_install_script is installed by running one of the following commands in your terminal. You can install this via the command-line with either curl or wget.

    wget https://raw.githubusercontent.com/jr0w3/glpi-fusioninventory-bash-install/main/glpi-install.sh && bash glpi-install.sh
or with curl

    curl -O https://raw.githubusercontent.com/jr0w3/glpi-fusioninventory-bash-install/main/glpi-install.sh && bash glpi-install.sh



Fix permission issue for logs

The log file could not be created in /var/www/html/glpi/files/_log.The log file could not be created in /var/www/html/glpi/files/_log. seen in Setup > General


sudo chown -R www-data:www-data /var/www/html/glpi/files/_log

sudo chmod -R 755 /var/www/html/glpi/files/_log

