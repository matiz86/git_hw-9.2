Домашнее задание к занятию 9.2 «Система мониторинга Zabbix»  SKOPKIN ILYA


Задание 1

![alt text](https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_matiz_13_03_2023_21_57_52.png)

# wget https://repo.zabbix.com/zabbix/6.4/debian/pool/main/z/zabbix-release/zabbix-release_6.4-1+debian11_all.deb
# dpkg -i zabbix-release_6.4-1+debian11_all.deb
# apt update
# apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
# sudo -u postgres createuser --pwprompt zabbix
# sudo -u postgres createdb -O zabbix zabbix
#zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
# nano  /etc/zabbix/zabbix_server.conf
# systemctl restart zabbix-server zabbix-agent apache2
# systemctl enable zabbix-server zabbix-agent apache2

Задание 2
Установите Zabbix Agent на два хоста.

https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_matiz_22_03_2023_19_34_54.png

https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_matiz_22_03_2023_19_35_26.png

https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_zabbix_test2_22_03_2023_21_33_07.png

https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_zabbix_test_22_03_2023_21_31_40.png



$ wget https://repo.zabbix.com/zabbix/6.2/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.2-4%2Bubuntu22.04_all.deb
$ sudo dpkg -i zabbix-release_6.2-4+ubuntu22.04_all.deb
$ sudo apt update
$ sudo apt install zabbix-agent2
$ sudo systemctl restart zabbix-agent2
$ sudo systemctl enable zabbix-agent2
$ sudo systemctl status zabbix-agent2
sudo nano /etc/zabbix/zabbix_agent2.conf
