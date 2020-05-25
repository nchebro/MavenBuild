HelloWorld Servlet example with corresponding Dockerfile

Use Maven Build first to create war file in Target folder.

mvn clean package

Artifact will be created in target folder.

docker build -t mavenbuild .

Once this is done u will be see image using docker images

Use below command to run the container

docker run -d -p 8080:8080 --name mavenbuild mavenbuild

Forked from Anuj's repository and testing PollSCM

Trying Jenkins build to execute shell command March 22 2020 Invoke top-level Maven targets - clean install GitHub - Jenkins WebHook Doing the change again for webhook config is working or not WebHook try3 Try4 with newKey 5th Try

5th Try was successful .. tyring again 6th time

publish java xml report webhook try

March 29 changed the ip

wget https://gist.githubusercontent.com/anujdevopslearn/8395705058c9cd4f4f5c3fec5591b246/raw/ca103bfd5a8791c805aaed30efc9c2cb192e7e72/apache.yml

ansible-playbook apache.yml

service apache2 status

wget https://gist.githubusercontent.com/anujdevopslearn/98a73c0ef7f72a70fc11759f8b2b9c25/raw/344bd206c7dbadfd56f32dc755c06e450c9b0d0f/mysql.yml

ansible-playbook mysql.yml

service mysql status

Tomcat Apache yml location

wget https://gist.githubusercontent.com/anujdevopslearn/efa28700a3b8aca18d2866aa2d24fa02/raw/b36e9eaa312d74ee68c21de06777ae07002b06a8/TomcatInstallation.yml

root@harishneo15yaho:/opt/apache-tomcat-8.5.53/bin# service tomcat status ● tomcat.service - Tomcat - instance Loaded: loaded (/etc/systemd/system/tomcat.service; disabled; vendor preset: enabled) Active: inactive (dead) root@harishneo15yaho:/opt/apache-tomcat-8.5.53/bin#

To Uninstall tomcat apache

https://gist.githubusercontent.com/anujdevopslearn/7f44b4505caa46da6b4bd66241044039/raw/21255d21ba75f05efae8df95e80a1dfaeb0d8026/TomcatUninstall.yml

Logs = = = =

root@harishneo15yaho:~# cat TomcatUninstall.yml
hosts: localhost vars:

http_port: 8088
tomcat_version: 8.5.53
tasks:

name: Make sure that we can connect to the machine ping:

name: Stop Tomcat shell: ./shutdown.sh args: chdir: /opt/apache-tomcat-{{ tomcat_version }}/bin/ become: true become_user: tomcat

name: Remove Tomcat file: path: /opt/apache-tomcat-{{ tomcat_version }} state: absent

name: remove user "tomcat" user: name: tomcat state: absent

name: remove group "tomcat" group: name: tomcat state: absent root@harishneo15yaho:# root@harishneo15yaho:# root@harishneo15yaho:# root@harishneo15yaho:# ansible-playbook TomcatUninstall.yml

PLAY [localhost] ****************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************** ok: [localhost]

TASK [Make sure that we can connect to the machine] ***************************************************************************************************************** ok: [localhost]

TASK [Stop Tomcat] ************************************************************************************************************************************************** changed: [localhost]

TASK [Remove Tomcat] ************************************************************************************************************************************************ changed: [localhost]

TASK [remove user "tomcat"] ***************************************************************************************************************************************** changed: [localhost]

TASK [remove group "tomcat"] **************************************************************************************************************************************** ok: [localhost]

PLAY RECAP ********************************************************************************************************************************************************** localhost : ok=6 changed=3 unreachable=0 failed=0 skipped=0 rescued=0 ignored=0

root@harishneo15yaho:~# cd /opt/ root@harishneo15yaho:/opt# ls -lrat total 194724 -rw-r--r-- 1 root root 3852 Sep 13 2016 zabbix-release_3.2-1+xenial_all.deb drwxr-xr-x 3 root root 4096 Nov 26 11:07 google -rw-rw-r-- 1 harishneo15yaho harishneo15yaho 189039090 Dec 6 10:35 eclipse-java-oxygen-3a-linux-gtk-x86_64.tar.gz drwxrwxr-x 8 root root 4096 Dec 6 10:55 eclipse -rw-r--r-- 1 root root 2662 Dec 7 07:40 1 -rw-r--r-- 1 root root 206 Dec 7 11:11 check_idletime.desktop drwxr-xr-x 5 root root 4096 Dec 8 12:22 .config drw-r-xr-x 10 root root 4096 Dec 12 10:06 91532 -rwxr-xr-x 1 root root 649 Dec 24 07:38 check_idletime.py -rw-r--r-- 1 root root 4153 Jan 3 10:02 linux_idletime.py drwxr-xr-x 23 root root 4096 Mar 29 16:34 .. -rw-r--r-- 1 root root 10300600 Mar 29 17:39 apache-tomcat-8.5.53.tar.gz drwxr-xr-x 6 root root 4096 Mar 29 17:52 . root@harishneo15yaho:/opt#

https://github.com/anujdevopslearn/AspDotNetDocker

https://github.com/anujdevopslearn/InterviewQuestions/blob/master/InstallationGuides/CleanServices.txt

curl https://assets.nagios.com/downloads/nagiosxi/install.sh | sh

https://assets.nagios.com/downloads/nagiosxi/docs/Installing-Nagios-XI-Manually-on-Linux.pdf

https://github.com/anujdevopslearn/InterviewQuestions/blob/master/InstallationGuides/CleanServices.txt

For cleanup

apt remove --purge mysql-server-core-5.7 mysql-server-5.7 mysql-server mysql-client mysql-client-5.7 apache2 jenkins nginx docker rm docker ps -a -q -f docker rmi docker images -q

=================
