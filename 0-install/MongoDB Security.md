### create user
use admin
db.createUser(
    {
    user: "admin",
    pwd: "admin",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
    }
)

### edit config
sudo vi /etc/mongod.conf
### and enable security
security:
  authorization: "enabled"
### restart mongod
sudo systemctl restart mongod
### and test it
mongo -u admin -p --authenticationDatabase admin


## Enable Remote Configuration
sudo ufw status
sudo ufw enable
sudo ufw allow OpenSSH
sudo ufw allow from Client_IP_Address to any port 27017
sudo ufw status
### configure public ip
sudo vi /etc/mongod.conf
### add the host ip
bindIp: 127.0.0.1,IP_of_MongoHost
sudo systemctl restart mongod
### test
mongo -u admin -p --authenticationDatabase admin --host IP_address_of_MongoHost



use admin
db.createUser(
  {
    user: "usradmin",
    pwd: "passwotrd",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)

db.createUser(
{
    user: "root",
    pwd: "passwotrd",
    roles: [ "root" ]
})



roles list:

read
readWrite
dbAdmin
userAdmin
clusterAdmin
readAnyDatabase
readWriteAnyDatabase
userAdminAnyDatabase
dbAdminAnyDatabase

create user:

db.createUser(user, writeConcern)

db.createUser({ user: "user",
  pwd: "pass",
  roles: [
    { role: "read", db: "database" } 
  ]
})

update user:

db.updateUser("user",{
  roles: [
    { role: "readWrite", db: "database" } 
  ]
})

drop user:

db.removeUser("user")

or

db.dropUser("user")

view users:

db.getUsers();