Download backup file from gdrive 

link = https://drive.google.com/file/d/1_PxQ2mBKYiASo3_Ov9ynFLYsT6ElQ2a7/view?usp=drive_link

untar .tgz file

$ tar -xzvf <file name>.tgz

Then remove /var/lib/jenkins

$ sudo rm -rf /var/lib/jenkins

Then move the extracted folder to /var/lib/jenkins

$ sudo cp -r <path>/var/lib/jenkins /var/lib/jenkins

Then change the ownership and permision  of the folder

$ sudo chown -R jenkins:jenkins /var/lib/jenkins
$ sudo chmod -R 755 /var/lib/jenkins

Then restart the jenkins service
$ sudo service jenkins restart


User will get reseted but job will restore

it will show login page but it will not accept the old user name and password

now change config.xml file

$ sudo sed -i 's/<useSecurity>true<\/useSecurity>/<useSecurity>false<\/useSecurity>/g' /var/lib/jenkins/config.xml

then restart the jenkins service

$ sudo service jenkins restart

then follow the video attached here to create a new user and password