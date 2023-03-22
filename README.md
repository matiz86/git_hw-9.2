Домашнее задание к занятию "9.2 «Zabbix. Часть 1»" - Skopkin Ilya

Задание 1
Установите Zabbix Server с веб-интерфейсом.

a. Установите репозиторий Zabbix

# wget https://repo.zabbix.com/zabbix/6.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.4-1+ubuntu22.04_all.deb
# dpkg -i zabbix-release_6.4-1+ubuntu22.04_all.deb
# apt update

b. Установите Zabbix сервер, веб-интерфейс и агент

# apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent

c. Создайте базу данных
Документация
Установите и запустите сервер базы данных.

Выполните следующие комманды на хосте, где будет распологаться база данных.

# sudo -u postgres createuser --pwprompt zabbix
# sudo -u postgres createdb -O zabbix zabbix

На хосте Zabbix сервера импортируйте начальную схему и данные.

# zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

d. Настройте базу данных для Zabbix сервера
Отредактируйте файл nano /etc/zabbix/zabbix_server.conf

e. Запустите процессы Zabbix сервера и агента

# systemctl restart zabbix-server zabbix-agent apache2
# systemctl enable zabbix-server zabbix-agent apache2  

![alt text] https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_matiz_22_03_2023_19_35_26.png


Задание 2
Установите Zabbix Agent на два хоста.

![alt text] https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_matiz_22_03_2023_19_34_54.png

![alt text] https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_zabbix_test2_22_03_2023_21_33_07.png

![alt text] https://github.com/matiz86/git_hw-9.2/blob/main/VirtualBox_zabbix_test_22_03_2023_21_31_40.png

sudo wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bubuntu22.04_all.deb
sudo dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
sudo apt update && sudo apt upgrade -y
sudo apt install zabbix-agent2 zabbix-agent2-plugin-*
sudo systemctl restart zabbix-agent2
sudo systemctl enable zabbix-agent2
sudo systemctl status zabbix-agent2.service
sudo nano /etc/zabbix/zabbix_agent2.conf 
