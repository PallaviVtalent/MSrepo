pipeline {
agent {
label 'Build server'
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
   
}
    
}
