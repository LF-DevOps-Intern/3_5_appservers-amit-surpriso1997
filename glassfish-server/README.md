### Installation of java glassfish server

1. Checking the java installation in the sytem:

```
java -version

```

If java command is not found we need to install java in the system.

It can be installed by running

```
 sudo apt-get install openjdk-8-jre

```

Locate the java installation directory, create and export **JAVA_HOME** variable in **~/.profile** file.Add the **...jdk/bin** in the **PATH** variable.

Run ` source ~/.profile` command to activate the changes.

Run `java -version` or `javac` commands to confirm the java installtion.

2. Downlaading and installing glassfish server:

[Download the glassfish server zip file from](https://download.oracle.com/glassfish/4.1.1/release/glassfish-4.1.1.zip)


Extract the zip file with **unzip** command. 

3. Create a new java ee web application project using intellij idea and add glass fish extraction path 
in the intellij's application server configuration 

4. Run the servelet program and build a .war file 

5. Change the defualt http port from 8080 to 8088 by edtiting the domain.xml file in 

``/home/manish/Downloads/glassfish-4.1.1/glassfish4/glassfish/domains/domain1/config`
``