
# Background

The Java portion of the course involves using a Java program to make the queries and updates that we have done using SQL.  The first question that arises then is why would we want to do such a thing? 

If you remember from our discussion on relational databases, there are three components to a database management system (DBMS).  This is the Database Application, the Database Engine and the actual Database.  

We have worked on the concept of  building Database schemas and working with them using CRUD.

You can argue that we have used some kind of graphical user interface by using SQL Developer, but this required us to know SQL and execute increasing complex queries.  We likely need a more user friendly GUI (with bottons, menue items etc) if our database will be used by someone that does not have knowledge of SQL.

To do this, we use Java to build an application.  But clearly our application needs to "talk" to the database and for this we need certain functions.  These functions or subroutines are collectively call the API - application specific interface.  This buzzword is thrown around a lot for many different applications but in essense an API defines a set of agreed upon functions needed to interact with our database.  

Now you do not have to be an expert to come to the realization that our Java program must also somehow "connect" to our database where all our nice tables/relations are.  We also need ways to write queries that will be converted to SQL queries.  So there are a lot of details that need to be taken care of, but fortunately, we do not care much about these details.  We simply abstract things and use them but it is still a good idea to get an idea of what is happening under the hood for all this magic to happen.

The API we use to interact with our database is called JDBC - Java Database Connectivity.  However, apart from the API, we also need a JDBC driver.  The details of this setup are explained in the Lynda.com video and <a href="http://www.tutorialspoint.com/jdbc/jdbc-driver-types.htm" target="_blank">in more detail here</a>.

Again, for our purposes, these details are not important.  You can think of the JDBC API as the methods or function declarations.  The JDBC driver is then the specific implementation or definition of these functions and these are specific to the vendor (as are specifc SQL commands).  How this API-Driver interaction occurs is a matter of detail and there are four different driver types which have historically progressed as new methods have taken over the old.  It is generally agreed that if you are building a GUI from scratch, you should use a <b>Type 4</b> driver unless there is a very good specific reason you do not want to do this.

# Software Download and Installation

We want to start by creating a skeleton Java project to connect to our SQL Server database and make queries.  We are roughly following the instructions in Chapter 2 of <a href="https://www.lynda.com/Java-tutorials/What-JDBC/110284/117302-4.html" target="_blank">Java: Database Integration with JDBC</a> 

Please watch the video, it is a good introdcution to JDBC API and drivers.  The setup uses MySQL and Eclipse rather than PL/SQL (Oracle version of SQL) and Netbeans, but the instructions can easily be adapted.  Follow the instructions below to setup a skeleton for running queries through Java.

As we just mentioned, the Lynda.com video tutorial uses <i>Eclipse</i> but we will use <i>Netbeans</i>.  What is the difference between Netbeans and Eclipse and which one should you use?  There is in fact no hard answer (although some experts in this area would strongly disagrea).  You may find <a href="https://stackoverflow.com/questions/330027/what-is-the-difference-between-eclipse-and-netbeans-if-i-want-to-use-only-the-ja" target="_blank"> this discussion on Stackoverflow where users give their opinion interesting</a>.

Anyways, let's get started.  First, we want to download Netbeans (if you have not done so already) from https://netbeans.org/downloads/index.html.  

Please note computer labs in school already have Netbeans installed, so if you do not want to download the software on your personal computer/laptop, just use a school computer and skip to the instructions on project setup.

I suggest choosing Java EE as shown below:

<img src="NetbeanDownload.png" alt="Netbeans Download" style="width:128px;height:128px;">

If the installer cannot find a compatible JDK installation on your system, you should Cancel the installation and install the following instead http://www.oracle.com/technetwork/java/javase/downloads/jdk-netbeans-jsp-142931.html

# Setting up the Java Project
To test your installation, Open up Netbean and then from the menu bar choose File->New Project->Java->Java Application->Next as shown below:

<img src="javaProject1.png" alt="New Java Project" style="width:128px;height:128px;">

Choose a project name and directory (doesn't really matter where):

<img src="javaProject2.png" alt="New Java Project" style="width:128px;height:128px;">

Click finish.

Add: System.out.println("Hello World!"); to your main function and choose Run.  You should see a successful Build (and Hello World! in the output window).

Download ojdbc6.jar from blackboard (under Lectures, Lecture 8) and follow the video tutorial on setting up the rest of the environment (it is a good idea to just watch the video once, then go over it again while setting up the environment).  Remember the video uses MySQL and HyperSQL, our connection string will be ("jdbc:oracle:thin:@apollo.humber.ca:1521:msit").

Your final project should look something like this and when you run it you should get a confirmation that you connected.

<img src="conection.png" alt="Java project with connection to SQL Server" style="width:128px;height:128px;">

Once done, you can do some basic queries (also shown in the video).

