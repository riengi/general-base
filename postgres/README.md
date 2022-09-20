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

### Switch to posgres (Linux) user
```sudo su - postgres```

### Set (DB) admin user (as postgres Linux user)
```
psql -c "alter user postgres with password 'postgres_password'"
```

### Create user for new database
```
createuser dbuser
```

### Create new database and give control to dbuser (from psql client)
```
createdb db -O dbuser
```

### Set password for dbuser (from psql client)
```
alter user dbuser with password 'dbuser_password';
```

### List database (from shell)
```
psql -l
```