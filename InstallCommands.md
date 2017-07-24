# Configurations

#install pgsql

sudo apt-get update

sudo apt-get install postgresql postgresql-contrib

sudo apt-get install postgresql-client

sudo -i -u postgres

sudo -u postgres createuser --interactive


#Move data directory to Mounting drive

sudo -u postgres psql

SHOW data_directory;

\q

service postgresql stop

service postgresql status

sudo rsync -av /var/lib/postgresql /mnt/volume-nyc1-01

sudo mv /var/lib/postgresql/9.5/main /var/lib/postgresql/9.5/main.bak

sudo nano /etc/postgresql/9.5/main/postgresql.conf

edit: => data_directory = '/mnt/volume-nyc1-01/postgresql/9.5/main'

service postgresql start

service postgresql status

sudo -u postgres psql

SHOW data_directory;
