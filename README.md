# SpringMVCxml


Why we use pom.xml file in spring mvc
POM stands for “Project Object Model”, This is a file which contain all Maven Configuration for building a project.

<project> element is the root element of this POM file.
          There are following possible children of this element with short description.

<modelVersion > 4.0.0 is a child element of <project>.
                It is currently describing the support for Maven 2 and Maven 3 versions.
                
<groupId> is a child element of <project>. 
          It is universally unique identifier for project, as a normal to use fully qualified package name
          to distinguish similar project names
          
<artifactId> is a child element of <project>. It is a unique identifier within group by the group Id. 
             Artifact Id is produced by Maven for project include JARs, Wars etc.
<packaging> is a child element of <project>. If you are running a command “maven clean install” It’ll generate .
            war file with artifactId. There is in this project we have a name of ArtifactId is SpringMVC so our generated file will be SpringMVC.war in target direct of project.
            
<version> is a child element of <project>. It is a version number of current project.
<name> is a child element of <proect>. It is a full name of Project.
<url> is a child element of <project>. It is a project’s home page URL.
<properties> is a child element of <project>. The various plugins use these project properties.
<java-version> is a child element of <properties>. The Java version for plugin use
<org.springframework-version> is a child element of <properties>. The Spring frame work version for plugin use.
<dependencies> is a child element of <project>. This element describes all dependencies associated with a project. They are automatically downloaded from repositories for this project.
<dependency> is a child element of <project>. It is a element for downloading and installing dependency.
<groupId> is a child element of <dependency>. It is a unique identifier for  project group, which is produced for dependency.
<artifactId> is a child element of <dependency>. It is a unique identifier for artifact.
<version> is a child element of <dependency>. It is a version of dependency


Why we use application contenxt file in spring mvc?
This fie is used when Spring configuration is provided to Application by application context file. It defines beans at root webapp context.

By <context:annotation-config/> element, we tells application to activate beans already registered in application context. It gives general support for annotation Like @Required, @Autowired, @PostConstructor
By <context:component-scan base-package=”com”/> element, we tells application to activate beans already registered in application context and scan package to find, register beans in application context.
By < mvc:annotation-driven /> element, we gives application to support for annotation-driven MVC Controllers Like @RequestMapping, @Controller, @RequestBody, @ResponseBody
By < mvc:resources mapping=”/resources/**” location=”/resources/” /> element,
<mvc:annotation-driven /> is to tell that you can define spring beans dependencies without defining much elements in xml or implements interface or extends a class.
@Repository is to tell that Class is a Dao without having to extend JpaDaoSupport or SubClass DaoSupport.
@Controller is to tell that Class having all methods to handle HTTP request without implements Controller interface or extends Sub class of Controllers.
<context:component-scan base-package=”com” /> is to tell that your spring application will search base package for scanning classes with @Controller, @Services, @Repository, or @Component
<mvc:resources mapping=”/resources/**” location=”/resources/” /> is tell that spring application needs to define path location and mapping to static resources like CSS, Images or JavaScripts.
<bean> is a java bean. Java Bean is a simple class with private fields and setter, getter methods. In XML we can defined it for usage. So here in this file three of beans tags are used with properties. Each property is like Class Private Field.
DataSource Bean: There are two attribute defined in this bean.
ID is defined for Unique Identifier for this bean as “dataSource”
CLASS is defined for reference type of “org.apache.commons.dbcp.BasicDataSource”.
BasicDataSource of Apache Commos is used for interaction with Relational Database. It helps for creating a new connection for an application.
Properties of BasicDataSource class:
driverClassName: The JDBC Driver Class Name to be used.
url: The connection URL to be passed to JDBC driver to establish a connection.
username: The connection username to be passed to JDBC driver to establish a connection.
password: The connection password to be passed to JDBC driver to establish a connection.
SessionFactory Bean: There are two attribute defined in this bean.
ID Is defined for Unique Identifier for this bean as “sessionFactory”
CLASS is defined for reference type of “org.springframework.orm.hibernate4.LocalSessionFactoryBean”.
Properties of LocalSessionFactoryBean class:
dataSource: SessionFactory uses dataSource properties. There is ref a attribute for referring bean by its ID.
packagesToScan: To specify packages to search for autodetection of entity classes in the classpath.
hibernateProperties : It sets hibernate properties.
hibernate.dialect: To specify correct database Dialect. Each Database has different SQL code generator.
hibernate.show_sql: Write all SQL statements to CONSOLE
hibernate.default_schema: Qualifies unqualified Table names with Given TableName and Schema Name.
format_sql: Pretty print the SQL in Console and LOG.
use_sql_comments: Hibernate will generate Comments inside SQL.
TransactionManager Bean: There are two attribute defined in this bean.
ID Is defined for Unique Identifier for this bean as “transactionManager”
CLASS is defined for reference type of “org.springframework.orm.hibernate4.HibernateTransactionManager”.
Properties of HibernateTransactionManager Class: 
This transaction manager is appropriate for applications that use a single Hibernate SessionFactory for transactional data acces


WEB.xml : It is a configuration file for web application in java. It instructs the servlet container (Tomcat) which class to load.
Filters could be defined in it.
Welcome file list could be defined in it.
Error pages could be defined in it.
Init-param: It is a static parameter, which is defined within servlet tag.It is a servlet level scope. At the servlet level you can get value of this.
Context-param: It is a static parameter, which is defined in web.xml file. It is an application level scope parameter. If the data does not change frequently you can store in it.
Servlet: The servlet element contains the declarative data of a servlet.
Servlet-Mapping: The servlet-mapping element defines a mapping between a servlet and a URL pattern.
Listener: The Listener element defines an event of the web application.

