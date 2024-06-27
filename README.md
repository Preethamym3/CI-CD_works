Insalled tomcat and added user for it one server.(instance:my_web_server)

another server installed docker, run the jenkins image and login to jenkins via web (instance: Docker)
  inside jenkins container in this path its installed /var/jenkins_home/   pwd at :/var/jenkins_home/secrets/initialAdminPassword
       uname:jenkinsuser
       pwd:jenkinsuser@123
       jenkinsuser@gmail.com jenkinsuser  url: http://54.80.107.17:8080/

lgin to tomcat server and /opt/tomcat/startup.sh run it and use the username and password and add that to jenkins > profile> credentials> global> create the creds (ccredentials id: webservercred)

<role rolename="manager-gui"/>
  <role rolename="manager-script"/>

  <user username="preetham" password="preetham123" roles="manager-gui,admin-gui,admin-script"/>
   <user username="admin" password="admin123" roles="manager-script,manager-jmx,manager-status,admin-gui"/>
in jenkins file edit the deply dection by ip credid and location of the sourcecode and files
  add maven tool for jenkins
 manage jenkins > tools> add maven (version same as jenkins)
 
