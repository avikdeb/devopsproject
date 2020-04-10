# Jenkins Installation Notes

## Prerequisites

### 1. Provision of AWS EC2 instance for all lab works
1. Refer C01-AWS-Lab-setup.pdf file kept in devopsproject repository and in Classroom shared drive
2. Install wget utility: sudo yum install wget, in case not found

### 2. Install Open JDK 8 and configure JAVA_HOME environment variable
Use the following commands:
1. sudo yum update
2. sudo yum install java-1.8*
3. Get the java installation home: find /usr/lib/jvm/java-1.8* | head -n 3
   <br>
   (Usually it is found in /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.amzn2.0.1.x86_64)
4. Modify .bash_profile file as:
   <br>
   export JAVA_HOME=/path-to-java-installation/
   <br>
   (e.g. JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.amzn2.0.1.x86_64)
5. Append this to your PATh variable as: PATH=$PATH:$JAVA_HOME/bin:$JAVA_HOME/lib
6. Save the .bash_profile file with vi command in Esc mode: :wq!
7. To take immediate effect: source ~/.bash_profile
8. Run: echo $JAVA_HOME followed by java -version and javac -version - They should yird correct results
  
### 4. Install Apache Maven and configure M2_HOME environment variable
Use the following commands:
1. Search for download apache maven in google
2. Go to the binary file (.gz) location, right click and copy link
3. Login to your EC2 instance, cd to some suitable location where you intend to install maven (could be the user home) and run: wget (paste the link copied in previous step). This will download maven binary (.gz) archive in that location
4. Unzip the downloaded archive: tar -xvf maven-archive-name.gz
5. Go to the archive dit=rectory and copy the path
6. open the ~/.bash_profile file and add another environment variable M2_HOME (like JAVA_HOME): export M2_HOME=/path-to-maven-instllation/
7. Append to PATH variable as before: PATH=$PATH:$JAVA_HOME/bin:$JAVA_HOME/lib:$M2_HOME/bin
8. Run: source ~/.bash_profile
9. Check with: mvn -version

<br>

## Install Jenkins
Follow the below steps once prerequisites are met.
1. Run: sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
2. Run: sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
3. Run: sudo yum -y install jenkins
4. To run jenkins as a service, run: sudo service jenkins start
5. To auto-restart of the service upon machine booting, run: sudo chkconfig jenkins on
6. To verify the auto-restart of the service upon machine booting, run: sudo chkconfig --list

<br>

## Post-Install Tasks
1. Once installation completes, Jenkins will prompt for one-time admin password to unlock product. Copy the path given in the
wizard and just paste in to your browser, right after the Jenkins URL. Alternatively, remote login to the box and run: sudo cat /path-to-key/
2. Proceed as usual and install suggested plug-ins. Few plug-ins may fail, don't worry - just continue as-is. They can be installed later when required
3. In First Admin User screen, provide an admin user name and password and click on Save and Continue. ***Do not simply continue as admin***
4. Once the dashboard screen opens, log out and log in again
5. Jenkins is now fully functional
