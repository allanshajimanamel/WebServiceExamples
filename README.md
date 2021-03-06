# WebServiceExamples

The repository contains my practice implementation for <b>SOAP</b> based and <b>REST</b> based webservices. The webservices created are used to perform create, read and update operations on a <b>Person</b> entity. A person entity has an <b>id, name and age</b>. 

The project structure was created using <b>Maven</b>.<br>
1. The main project here is <b>webservices</b> which build the whole project and updates the EAR.<br>
2. The project <b>webservices-server</b> contains the backened implementation. I used <b>EJB 3.1 and JPA 2.0</b> for the implementation.<br>
3. The project <b>webservices-api</b> contains the interface to the project <b>webservices-server</b>. This was done so that the webservice and backend can be developed independently of each other and also provide of distributed deployment.<br>
4. The project <b>webservices-ear</b> is the ear for the implementation.<br>
5. The project <b>webservices-soap</b> contains the SOAP based web service.<br>
6. The project <b>webservices-rest</b> contains the rest based web service.<br>

I use <b>Wildfly 8.2</b> as my application server and <b>MySQL 5</b> as my database server.

For the SOAP based web service I am using <b>Apache CXF</b> to create the web service in a bottom up approach. Since I am using Wildfly 8.2, I am using the Apache CXF library provided by the JBoss ws which is inbuilt into the server. If we use our own Apache CXF implementation we will get class loading exceptions. If we are to build it for any other server, like Tomcat, then we have to provide the implementation of Apache CXF and generate the wsdl from code.<br>
Since Wildfly 8.2 has a full fledged J2EE container with JBoss ws we do not generate the wsdl or schema for the messages. It will be created by JBoss when we deploy the application using its provided Apache CXF library.

For the REST based web service I am using the JBoss RestEasy API and Jackson API.
