# jojokz.github.io

[Webpage on Engineering using no code framework](https://exp.gndec.ac.in/j)

[My webpage on social media addiction](https://exp.gndec.ac.in/j)

[ERP Next installation Tutorial ,check out this link](ERPNext.docx)

ERPNext-installation-Guide
STEP 1 Install git
Git is the most commonly used version control system. Git tracks the changes you make to files, so you have a record of what has been done, and you can revert to specific versions should you ever need to. Git also makes collaboration easier, allowing changes by multiple people to all be merged into one source.

sudo apt-get install git
STEP 2 install python-dev
python-dev is the package that contains the header files for the Python C API, which is used by lxml because it includes Python C extensions for high performance
sudo apt-get install python3-dev



STEP 3 Install setuptools and pip (Python's Package Manager).
Setuptools is a collection of enhancements to the Python distutils that allow developers to more easily build and distribute Python packages, especially ones that have dependencies on other packages. Packages built and distributed using setuptools look to the user like ordinary Python packages based on the distutils.

pip is a package manager for Python. It's a tool that allows you to install and manage additional libraries and dependencies that are not distributed as part of the standard library.

sudo apt-get install python3-setuptools python3-pip
STEP 4 Install virtualenv
virtualenv is a tool for creating isolated Python environments containing their own copy of python , pip , and their own place to keep libraries installed from PyPI. It's designed to allow you to work on multiple projects with different dependencies at the same time on the same machine.

sudo apt-get install virtualenv
CHECK PYTHON VERSION

python3 -V
IF VERSION IS 3.8.X RUN

sudo apt install python3.8-venv
IF VERSION IS 3.10.X RUN

 sudo apt install python3.10-venv
STEP 5 Install MariaDB 10.3 stable package
MariaDB is developed as open source software and as a relational database it provides an SQL interface for accessing data.

open this link


For ubuntu 20.04

sudo apt-get install software-properties-common
sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'
sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el] https://ftp.icm.edu.pl/pub/unix/database/mariadb/repo/10.3/ubuntu focal main'
sudo apt update
sudo apt install mariadb-server
For ubuntu 18.04

sudo apt-get install software-properties-common dirmngr apt-transport-https
sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'
sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el] https://mirrors.aliyun.com/mariadb/repo/10.3/ubuntu bionic main'
sudo apt update
sudo apt install mariadb-server
IMPORTANT :During this installation you'll be prompted to set the MySQL root password. If you are not prompted for the same You can initialize the MySQL server setup by executing the following command

sudo mysql_secure_installation

During the setup process, the server will prompt you with a few questions as given below. Follow the instructions to continue the setup;
•	Enter current password for root: (Enter your SSH root user password)
•	Switch to unix_socket authentication [Y/n]: Y
•	Change the root password? [Y/n]: Y
It will ask you to set new MySQL root password at this step. This can be different from the SSH root user password.
•	Remove anonymous users? [Y/n] Y
•	Disallow root login remotely? [Y/n]: N
This is set as N because we might want to access the database from a remote server for using business analytics software like Metabase / PowerBI / Tableau, etc.
•	Remove test database and access to it? [Y/n]: Y
•	Reload privilege tables now? [Y/n]: Y

STEP 6 MySQL database development files
sudo apt-get install libmysqlclient-dev
STEP 7 Edit the mariadb configuration ( unicode character encoding )
sudo nano /etc/mysql/my.cnf
add this to the my.cnf file

[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci

[mysql]
default-character-set = utf8mb4
Now press (Ctrl-X) to exit

sudo service mysql restart
STEP 8 install Redis
Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache, and message broker.

sudo apt-get install redis-server
STEP 9 install Node.js 14.X package
Node.js is an open source, cross-platform runtime environment for developing server-side and networking applications. Node.js applications are written in JavaScript, and can be run within the Node.js runtime on OS X, Microsoft Windows, and Linux.

sudo apt-get install curl
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
STEP 10 install Yarn
Yarn is a JavaScript package manager that aims to be speedy, deterministic, and secure. See how easy it is to drop yarn in where you were using npm before, and get faster, more reliable installs. Yarn is a package manager for JavaScript.

sudo npm install -g yarn
STEP 11 install wkhtmltopdf
Wkhtmltopdf is an open source simple and much effective command-line shell utility that enables user to convert any given HTML (Web Page) to PDF document or an image (jpg, png, etc)

sudo apt-get install xvfb libfontconfig wkhtmltopdf

STEP 12 install frappe-bench
sudo -H pip3 install frappe-bench


bench --version
STEP 13 initilise the frappe bench & install frappe latest version
bench init frappe-bench --frappe-branch version-13

cd frappe-bench/
bench start
STEP 14 create a site in frappe bench
bench new-site dcode.com
STEP 15 install ERPNext latest version in bench & site
bench get-app erpnext --branch version-13
###OR
bench get-app https://github.com/frappe/erpnext --branch version-13

bench --site dcode.com install-app erpnext

bench start

