#  **<span style="color:green">Buamtech, Vancouver, Canada.</span>**
### **<span style="color:green">Contacts: +1(236) 668 8271<br> WebSite : <http://buamtech.ca/></span>**
### **Email: abridevops@.com**



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
### Install Tomcat version 9.0.73
``` sh
sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.65/bin/apache-tomcat-9.0.73.tar.gz
sudo tar -xvf apache-tomcat-9.0.73.tar.gz
sudo rm -rf apache-tomcat-9.0.73.tar.gz
sudo mv apache-tomcat-9.0.73 tomcat9
sudo chmod 777 -R /opt/tomcat9
sudo chown ec2-user -R /opt/tomcat9
sh /opt/tomcat9/bin/startup.sh
# create a soft link to start and stop tomcat
sudo ln -s /opt/tomcat9/bin/startup.sh /usr/bin/starttomcat
sudo ln -s /opt/tomcat9/bin/shutdown.sh /usr/bin/stoptomcat
starttomcat
sudo su - ec2-user
```

