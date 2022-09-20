# Posgres 

### Install (Ubuntu 22.04)
```sudo apt install postgresql postgresql-client```

### Check service status
```systemctl status postgresql.service ```

### Set Listening IP 
```
# /etc/postgresql/14/main/postgresql.conf

# Allow all incoming addresses
listen_address = '*'

# Allow specific address
listen_address = '192.168.1.10'
```

### Switch to posgres (Linux) user and run psql
```
sudo su - postgres
psql

# or oneline
sudo -u postgres psql

```

### Set (DB) admin user (as postgres Linux user)
```
alter user postgres with password 'postgres_password';
```

### Create user for new database
```
createuser dbuser;
```

### Create new database 
```
createdb db;
```

### Set password for dbuser (from psql client)
```
alter user dbuser with password 'dbuser_password';
```

### Grant all privileges on database to specific user
```
grant all privileges on database db to dbuser;
```

### List database (from shell)
```
psql -l
```
