**01.  Apache Tomcat 7 Installation**

**02.	Setting up the CATALINA_HOME and JAVA_HOME details**

**03.	Starting the Tomcat**

**04.	Deploying Sample ws application on Tomcat**

**05.	SSL Information**

***

**01.	Apache Tomcat 7 Installation**

Tomcat 7 Installation Link : 
http://www.reverse.net/pub/apache/tomcat/tomcat-7/v7.0.29/bin/apache-tomcat-7.0.29-windows-x86.zip

01.	Click the above link to download the Tomcat Server 7.

02.	Extract the zip file

03.	Copy the “apache-tomcat-7.0.29-windows-x86” to  your drive C:\ or D:\
Note : Tomcat 7.0 requires Java SE 6 or later. Read the RELEASE-NOTES and the RUNNING.txt file in the distribution for more details.

**02.	Setting up the CATALINA_HOME and JAVA_HOME details**

Make sure the that Java 6 or above is installed on your PC
Set the JAVA_HOME as below and follow the steps 1,2,3,4 same way configure the CATALINA_HOME also.


Show jdk path as JAVA_HOME and Tomcat 7 Location as CATALINA_HOME.

JAVA_HOME= C:\Program Files (x86)\Java\jdk1.6.0_33

CATALINA_HOME= C:\apache-tomcat-7.0.29


**03.	Starting the Tomcat**

Start the Tomcat as below

C:\apache-tomcat-7.0.29\bin\ startup.bat , If you are using unix please use startup.sh 

**Log file locations for Debugging**

  **To change the logging Directory of the Apache server :**

     ${catalina.base}/conf/logging.properties

  **To change the logging Directory of the JVM :**

    ${java.home}/lib/logging.properties

  **To change the logging Directory of the Web application**

      /WEB-INF/classes/logging.properties or any config  directory of your application where you have configured  your logging.properties file.

**04.	Deploying Sample webServices application on Tomcat**

Accessing the Tomcat Server with the below link. If you wanted to change the port number 8080 to something else please change In the  CATALINA_BASE/conf/server.xml.

     http://localhost:8080/sample/firstMobileIndex.jsp

I am accessing the sample page, I have deployed sample.war which contains firstmobileIndex.jsp .

To Manage the server as manger 

please make the below changes in CATALINA_BASE/conf/ tomcat-users.xml as

    <role rolename="manager-gui"/>
    <user username="admin" password="admin" roles="manager-gui"/>

**05.	SSL Information**

Tomcat can use two different implementations of SSL:
•	The JSSE implementation provided as part of the Java runtime (since 1.4)
•	The APR implementation, which uses the OpenSSL engine by default.

We can Import any existing certificate or we can raise our own self signed certificate and we can install

To import an existing certificate signed by your own CA into a PKCS12 keystore using OpenSSL you would execute a command like:
 	 	 
 	openssl pkcs12 -export -in mycert.crt -inkey mykey.key \
                        -out mycert.p12 -name tomcat -CAfile myCA.crt \
                        -caname root -chain	 
 	 	 

To create a new keystore from scratch, containing a single self-signed Certificate, execute the following from a terminal command line:

**Windows:**
 	 	 
 	%JAVA_HOME%\bin\keytool -genkey -alias tomcat -keyalg RSA	 
 	 	 	  	 
**Unix**
  	 	 
 	$JAVA_HOME/bin/keytool -genkey -alias tomcat -keyalg RSA	 
 	 	 
      
This will create .keystore file in     **C:\Users\firstMobileAzhar\\.keystore**

You can specify the your own path where this file has to be generated.

    keytool -genkey -alias tomcat1 -keyalg RSA -keystore C:\apache-tomcat-7.0.29\Keystore.keystore
    
01.	Uncomment the "SSL HTTP/1.1 Connector" entry in $CATALINA_BASE/conf/server.xml and modify 
as described in the Configuration section below.
Un comment the below and add new line as shown after commented tag .
    <!--
    <Connector port="8443" protocol="HTTP/1.1" SSLEnabled="true"
               maxThreads="150" scheme="https" secure="true"
               clientAuth="false" sslProtocol="TLS" />
    -->

    <Connector port="8443" protocol="HTTP/1.1" SSLEnabled="true"
               maxThreads="150" scheme="https" secure="true"  
                keystoreFile="${user.home}/.keystore" keystorePass="changeit"
               clientAuth="false" sslProtocol="TLS" />

Please access the site below URL for https communication

    https://localhost:8443/ 



If it is giving any  Error “SSLCertificateFile must be defined when using SSL with APR”
APR/native connector with the SSL configuration for the JSSE connectors (BIO and NIO). The simplest fix will be to comment out the APR lifecycle listener in server.xml.
<Listener className="org.apache.catalina.core.AprLifecycleListener" SSLEngine="on" />

**Please follow the below link for further details**

    http://tomcat.apache.org/tomcat-7.0-doc/ssl-howto.html
