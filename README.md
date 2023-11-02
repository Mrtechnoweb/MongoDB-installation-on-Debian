# MySQL-installation-on-Debian
Install MySQL on Debian
Step1: cat /etc/os-release
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/8f399aa5-ad96-461d-963a-dcbafe9bbcec)
Step 2: Add MongoDB APT repository on Debian 11 by using the below command
install gnupg2 wget
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/c9ebd16a-3ab6-48a2-9047-99824cea1020)
Step 3: Add MongoDB APT repository by using the below command
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
echo "deb http://repo.mongodb.org/apt/debian buster/mongodb-org/5.0 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/063726f6-8973-4516-88a7-39e11e5d3a73)
Step 4: Update the packages by using the below command
apt update
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/fc0e5a47-7c34-4b98-9808-12d0e4515a56)
Step 5: Install MongoDB 5.0 the packages by using the below command
apt install mongodb-org
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/bf0eeabe-b33a-4a0c-b76c-5cea66356fa7)
Step 6: Check the Mangod version by using the below command
mongod --version
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/9ad758ef-6f4d-4419-b2aa-051d2a1d5ac0)
Step 7: Configure MongoDB by using the below command
systemctl start mongod
systemctl enable mongod
Step 8: Secure MongoDB 5.0 Instance by using the below command
mongosh
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/cabf6a17-2798-47b2-bf90-b0a211577541)
Step 9: Switch the Admin Database by using the below command
use admin
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/6e2f7228-e7e1-4915-ac7e-89c699ff9ef9)
Step 10: Create user in mongo Database by using the below command
db.createUser({
  user: "<username>",
  pwd: "<password>",
  roles: [
    {
      role: "readWrite",
      db: "mydb"
    }
  ]
})
Step 11: Show user in mongo Database by using the below command
show users
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/c7b4a970-9e66-44fc-b8a9-42effc342890)
Step 12: Edit the MongoDB configuration file and enable authentication.
nano /etc/mongod.conf
![image](https://github.com/Mrtechnoweb/MySQL-installation-on-Debian/assets/149655221/44839f68-b607-4a05-a4e6-72278c32f38c)
tep 13. Restart the mongo dB by using the below command
systemctl restart mongod
