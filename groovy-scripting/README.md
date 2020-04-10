# Groovy Installation Notes

<br>

### 1. Provision of AWS EC2 instance for all lab works
Refer C01-AWS-Lab-setup.pdf file kept in devopsproject repository and in Classroom shared drive

<br>

### 2. Install and Configure Java followed by Groovy on Linux
Use the following commands:
1. sudo yum update
2. sudo yum install java-1.8*
3. Get the java installation home: find /usr/lib/jvm/java-1.8* | head -n 3
   <br>
   (Usually it is found in /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.amzn2.0.1.x86_64)
4. If we want to set JAVA_HOME globally, append the file: sudo vi /etc/environment  and source it as: source /etc/environment - **Global system scope**
5. Set for all users: do the same in /etc/profile file and source the same - **Global user scope**
6. It we want to set JAVA_HOME as user level variable and to be seen in bash, create and append the file: .bash_profile (or straight in .bashrc) - **This is bash specific**
7. Do either point **4 or 5 or 6**
8. Install zip and unzip utlities, if not present
9. Run: curl -s get.sdkman.io | bash
10. Run: source "$HOME/.sdkman/bin/sdkman-init.sh"
11. Run: sdk install groovy
12. Check the installation with command: groovy --version and also run groovysh to get the groovy shell
13. Installation is complete

<br>

### 3. Install Groovy on Wndows
1. Download and install JDK (Oracle JDK 8), if not present beforehand. set JAVA_HOME environment variable and add JAVA_HOME/bin to your PATH environment variable
2. Download Groovy SDK - https://bintray.com/artifact/download/groovy/maven/apache-groovy-sdk-2.5.9.zip
3. Extract in your local windows m/c (say, C:\groovy) - This is your install_home
4. Set GROOVY_HOME environment variable to the install_home
5. Add GROOVY_HOME/bin to your PATH environment variable
6. Check the installation with command: groovy --version and also run groovysh to get the groovy shell
7. Installation is complete

<br>

## 4. Setting up of a modern Text Editor - Atom ***[optional]***
Atom is a very good text editor capable of intelligent code completion and lot of other developer friendly tasks. 
We will use this to develop our Groovy codes and also generate DSL scripts.
<br>
Download Link: https://atom.io/
<br>
1. Go to File > settings > Packages > Install language-groovy package and restart Atom
2. Start writing your codes - save files with .groovy extension

<br>
## 5.Sample codes
Groovy sample codes can be found in the repositoty - https://github.com/avikdeb/mygroovy
