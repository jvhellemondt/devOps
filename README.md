# devOps

---------

How To Install MySQL 8.0 On Ubuntu 18.04

Van <https://phoenixnap.com/kb/how-to-install-mysql-on-ubuntu-18-04> 

tail -30 /var/log/mysql/error.log
journalctl -xe

Install apparmor - nodig om mysql te herstarten


How to Optimize MySQL Performance Using MySQLTuner

Van <https://www.linode.com/docs/databases/mysql/how-to-optimize-mysql-performance-using-mysqltuner/> 

How to reduce the memory usage of MySQL
Van <https://tech.labelleassiette.com/how-to-reduce-the-memory-usage-of-mysql-61ea7d1a9bd> 

vim /etc/mysql/mysql.conf.d/mysqld.cnf
systemctl restart mysql
sh MySQL_mem_use_test (script van "How to reduce the memory usage of MySQL)
echo [PID]  [MEM]  [PATH] &&  ps aux | awk '{print $2, $4, $11}' | sort -k2rn | head -n 20

Performance schema, neemt standaard heel veel mem in beslag.
https://dev.mysql.com/doc/refman/8.0/en/memory-use.html
https://dev.mysql.com/doc/refman/8.0/en/performance-schema-system-variables.html

---------

https://support.rackspace.com/how-to/installing-mysql-server-on-ubuntu/

Om toegang van alle externe IP's toe te staan, geef als IP "%" op.

Bijv: GRANT ALL PRIVILEGES ON ddfs.* to "dbcf"@"%" WITH GRANT OPTION;

---------

mysql_config not found when installing mysqldb python interface
Van <https://stackoverflow.com/questions/7475223/mysql-config-not-found-when-installing-mysqldb-python-interface> 

---------

How to set up MySQL for remote access on Ubuntu Server 16.04Van <https://www.techrepublic.com/article/how-to-set-up-mysql-for-remote-access-on-ubuntu-server-16-04/> 
GRANT ALL privileges ON ddfs.* TO "dbcf"@"%" IDENTIFIED BY "Jens@Work2019!" WITH GRANT OPTION;
Met SSL: GRANT ALL privileges ON ddfs.* TO "dbcf"@"%" IDENTIFIED BY "Jens@Work2019!" REQUIRE SSL;

---------

Installing The Latest Python 3.7 On Ubuntu 16.04 | 18.04
Van <https://websiteforstudents.com/installing-the-latest-python-3-7-on-ubuntu-16-04-18-04/> 

---------

How to Install Nginx Latest Version on Ubuntu 16.04 and Ubuntu 16.10

Van <https://www.linuxbabe.com/nginx/nginx-latest-version-ubuntu-16-04-16-10> 

---------

How To Install Git on Ubuntu 16.04 LTS
Van <https://www.liquidweb.com/kb/install-git-ubuntu-16-04-lts/> 

---------

How To Set Up a Firewall with UFW on Ubuntu 18.04
Van <https://linuxize.com/post/how-to-setup-a-firewall-with-ufw-on-ubuntu-18-04/> 

UFW Essentials: Common Firewall Rules and Commands
Van <https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands> 

---------

Setting up Django and your web server with uWSGI and nginx
Van <https://uwsgi-docs.readthedocs.io/en/latest/tutorials/Django_and_nginx.html#basic-uwsgi-installation-and-configuration> 

sudo usermod -a -G groupName userName

Zorg ervoor dat je de virtualenv map (via virtualenvswrapper) niet in de map van profiel ROOT zet. Nginx start automatisch op met profiel www-data. Www-data moet toegang hebben tot de desbetreffende ingestelde virtualenv in de virtualenv map. Daarnaast moet Www-data toegang hebben tot de map waarin de daadwerkelijke website staat.
Bash command : sudo chown <your username>:<your usergroup> -R <path to>/.blabla
-R in het bash command zorgt ervoor dat alle onderliggende mappen ook van opgegeven profiel worden.
Om root alsnog rechten te geven tot de mappen van www-data, zorg je dat root behoort tot de usergroup van www-data.

---------

Virtualenwrapper
https://virtualenvwrapper.readthedocs.io/en/latest/install.html

Installed virtualenv and virtualenvwrapper: Python says no module named virtualenvwrapper
Van <https://stackoverflow.com/questions/23997403/installed-virtualenv-and-virtualenvwrapper-python-says-no-module-named-virtuale> 

---------

uWSGI vs. Gunicorn
Van <https://blog.kgriffs.com/2012/12/18/uwsgi-vs-gunicorn-vs-node-benchmarks.html> 

---------

Django - install on Ubuntu
https://tecadmin.net/install-django-on-ubuntu/

---------

NginX - server opnieuw opstarten/configureren
sudo service nginx configtest  # make sure the config is good before reloading!
sudo service nginx reload
https://www.strato.nl/server/nginx-configureren/
https://www.strato.nl/server/nginx-tutorial-eerste-stappen-met-nginxconf/

---------

How To Serve Django Applications with uWSGI and Nginx on Ubuntu 16.04
Van <https://www.digitalocean.com/community/tutorials/how-to-serve-django-applications-with-uwsgi-and-nginx-on-ubuntu-16-04> 

---------

How to grant super privilege to the user?
Van <https://dba.stackexchange.com/questions/63404/how-to-grant-super-privilege-to-the-user> 

---------
Ubuntu server setup checklist
https://www.process.st/checklist/ubuntu-server-setup-process/

Server security checklist
https://www.process.st/checklist/server-security-checklist

Ik raad aan om: 
•	de poorten (zeker 3306) enkel toe te staan vanaf de Govers IP range (en eventueel een paar andere). Beter nog: Alles dicht zetten, behalve wat open moet staan.
Hierdoor kan mysql enkel vanaf vertrouwde omgevingen benaderd worden.
•	fail2ban te gebruiken om bij failed login attempts IP's te blokkeren. 
Hierdoor kan, wanneer met toch poort 7822 gevonden heeft, 

SSH beveiliging
https://www.linuxbabe.com/ubuntu/two-factor-authentication-ssh-key-ubuntu-18-04

5 Effective Tips to Harden SSH Server on Ubuntu
Van <https://www.linuxbabe.com/security/harden-ssh-server> 

34 Linux Server Security Tips & Checklists for Sysadmins
Van <https://www.process.st/server-security/> 

---------

Delete lines in a text file that contain a specific string
Van <https://stackoverflow.com/questions/5410757/delete-lines-in-a-text-file-that-contain-a-specific-string> 

---------

How to Upgrade Linux Kernel in Ubuntu 16.04 Server
Van <https://www.howtoforge.com/tutorial/how-to-upgrade-linux-kernel-in-ubuntu-1604-server/> 
https://kernel.ubuntu.com/~kernel-ppa/mainline/


wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.2.7/linux-headers-5.2.7-050207_5.2.7-050207.201908061831_all.deb
wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.2.7/linux-headers-5.2.7-050207-generic_5.2.7-050207.201908061831_amd64.deb
wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.2.7/linux-image-unsigned-5.2.7-050207-generic_5.2.7-050207.201908061831_amd64.deb
Wget https://kernel.ubuntu.com/~kernel-ppa/mainline/v5.2.7/linux-modules-5.2.7-050207-generic_5.2.7-050207.201908061831_amd64.deb

Werkt niet op VPS.
