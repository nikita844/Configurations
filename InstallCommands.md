# Configurations

#install pgsql

sudo apt-get update

sudo apt-get install postgresql postgresql-contrib

sudo apt-get install postgresql-client

sudo -i -u postgres

sudo -u postgres createuser --interactive






sudo -u postgres psql

SHOW data_directory;

\q

service postgresql stop

service postgresql status

sudo rsync -av /var/lib/postgresql /mnt/data_dir

sudo mv /var/lib/postgresql/9.3/main /var/lib/postgresql/9.3/main.bak

sudo nano /etc/postgresql/9.3/main/postgresql.conf

edit: => data_directory = '/mnt/data_dir/postgresql/9.3/main'

service postgresql start

service postgresql status

sudo -u postgres psql

SHOW data_directory;


#set password

sudo -u postgres psql postgres

\password postgres



#install PostGis


sudo apt-get install -y postgis postgresql-9.3-postgis-2.1



#install rabbitmq

wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb

sudo dpkg -i erlang-solutions_1.0_all.deb

sudo apt-get update

sudo apt-get install erlang

echo 'deb http://www.rabbitmq.com/debian/ testing main' |
     sudo tee /etc/apt/sources.list.d/rabbitmq.list
     
wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc |
     sudo apt-key add -
     
     
sudo apt-get update
     
     
sudo apt-get install rabbitmq-server


rabbitmq-plugins enable rabbitmq_management


#add User in rabbitmq
rabbitmqctl add_user newadmin s0m3p4ssw0rd
rabbitmqctl set_user_tags newadmin administrator
rabbitmqctl set_permissions -p / newadmin ".*" ".*" ".*"

     

