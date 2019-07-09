# tomcat
Bastille Template for Tomcat Jail

After installing Tomcat, you need to edit the 
/usr/local/apache-tomcat-9.0/conf/tomcat-users.xml file to put in the correct users 
for your installation.  The file looks like the following:

#######

<tomcat-users xmlns="http://tomcat.apache.org/xml"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://tomcat.apache.org/xml tomcat-users.xsd"
              version="1.0">


<role rolename="manager-gui"/>
 <role rolename="manager-script"/>
 <role rolename="manager-jmx"/>
 <role rolename="manager-status"/>
 <role rolename="admin-gui"/>
 <role rolename="admin-script"/>
 <user username="admin" password="admin" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-gui,admin-script"/>


</tomcat-users>

#######

Then you can restart tomcat with:

	service tomcat restart


Once this is done you can test to make sure tomcat is running by doing the following:

	service tomcat status


	netstat -an | grep 8080


and open the following in a browser:
	
	http://[IP]:8080  or http://hostname:8080

and you should see the tomcat configuration page.

Done!


