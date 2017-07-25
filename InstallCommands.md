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
