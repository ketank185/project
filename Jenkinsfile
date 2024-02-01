pipeline { 
agent { 
label { 
label "built-in" 
customWorkspace "/mnt/projects" 
} 
} 
environment { 
url = "https://github.com/Shantanumajan6/project.git" 
} 
stages { 
stage ("ClONE_PROJECT"){ 
steps { 
sh "rm -rf *" 
sh "git clone $url"  
} 
}  
stage ("BUILD_PROJECT") { 
steps { 
sh "cd project && mvn clean install" 
} 
} 
stage ("COPY") { 
steps { 
sh "rm -rf /mnt/wars/*" 
sh "sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.85/bin/apache-tomcat-9.0.85.zip"
sh "unzip apache-tomcat-9.0.85.zip"
sh "sudo chmod -R 777 /mnt"
sh "cd /mnt/wars/apache-tomcat-9.0.85/bin && ./startup.sh"
sh "scp -r /mnt/projects/project/target/LoginWebApp.war amar@10.0.1.5:/mnt/wars"
} 
} 
} 
} 
