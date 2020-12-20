pipeline {
agent {
label 'Buildserver'
}

stages {

stage ('Checkout') 
{
steps
    {
    
        checkout scm
        
    }
    
}
        stage('Build')
    {
            steps {
                
                sh "cd /home/ubuntu/workspace/jenkinspipeline/account-service; mvn clean install "
                 
            }
        }
   
    stage ('dockerbuild') 
{
    steps
    {
       sh "cd /home/ubuntu/workspace/jenkinspipeline/account-service ; sudo docker build -t account-service . " 
    }
}
     stage ('dockerimagepush ') 
{
    steps
    {
       sh "cd /home/ubuntu/workspace/jenkinspipeline/account-service ; sudo  docker login -upallavivardhanapu -p@Pa19021995 "
        sh "cd /home/ubuntu/workspace/jenkinspipeline/account-service ; sudo docker tag account-service pallavivardhanapu/account-service  "
        sh "cd /home/ubuntu/workspace/jenkinspipeline/account-service ; sudo docker push pallavivardhanapu/account-service   "
        
        
    }
}

stage ('k8s deployment') 
{
    steps 
    {
    node ('Ansible')
    {
       sh " sudo ansible-playbook /root/k8s.yaml" 
    }
}   
}
    
}
}
