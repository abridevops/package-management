#  **<span style="color:green">Landmark Technologies, Ontario, Canada.</span>**
### **<span style="color:green">Contacts: +1437 215 2483<br> WebSite : <http://mylandmarktech.com/></span>**
### **Email: mylandmarktech@gmail.com**



## Apache Tomcat Installation And Setup In AWS EC2 Redhat Instance.
##### Prerequisite
+ AWS Acccount.
+ Create Redhat EC2 T2.micro Instance.
+ Create Security Group and open Tomcat ports or Required ports.
   + 8080 ..etc
+ Attach Security Group to EC2 Instance.
+ Install java openJDK 1.8+

### Install Java JDK 1.8+ 

``` sh
# install Java JDK 1.8+ as a pre-requisit for tomcat to run.
cd /opt 
sudo yum install git wget -y
sudo yum install java-1.8.0-openjdk-devel -y
# Download tomcat software and extract it.
sudo yum install wget unzip -y
```
### Install Tomcat version 10.1.7
``` sh
sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.65/bin/apache-tomcat-10.1.7.tar.gz
sudo tar -xvf apache-tomcat-10.1.7.tar.gz
sudo rm -rf apache-tomcat-10.1.7.tar.gz
sudo mv apache-tomcat-10.1.7 tomcat10
sudo chmod 777 -R /opt/tomcat10
sudo chown ec2-user -R /opt/tomcat10
sh /opt/tomcat10/bin/startup.sh
# create a soft link to start and stop tomcat
sudo ln -s /opt/tomcat10/bin/startup.sh /usr/bin/starttomcat
sudo ln -s /opt/tomcat10/bin/shutdown.sh /usr/bin/stoptomcat
starttomcat
sudo su - ec2-user
```

