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
stage ("COPY") { 
steps { 
sh "rm -rf /mnt/wars/*" 
sh "cp -r /mnt/projects/target/LoginWebApp.war /mnt/wars" 
} 
} 
} 
} 
