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
sh "scp -r /mnt/projects/project/target/LoginWebApp.war amar@10.0.1.5:/mnt/wars"
} 
} 
} 
} 
