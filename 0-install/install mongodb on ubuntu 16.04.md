### import the key for the official MongoDB repository
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

### add MongoDB repository details so apt will know where to download the packages
echo "deb [ arch=amd64,arm64 ] http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

### update the packages list
sudo apt-get update

### we'll install themongodb-org meta-package, which includes the daemon, configuration and init scripts, shell, and management tools on the server
sudo apt-get install mongodb-org
sudo systemctl start mongod
sudo systemctl status mongod
sudo systemctl enable mongod

