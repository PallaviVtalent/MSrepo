pipeline {
agent {
label '24thlinuxnode'
}

stages {

stage ('Checkout') 
{
steps
    {
    
        checkout scm
        
    }
    
}
        stage('Build') {
            steps {
                sh "cd /home/ubuntu/workspace/PipelineJob/account-service ; mvn clean install "
                echo "Will deploy to ${BUILD_ENV}"
               echo "Will deploy to ${params.BUILD_ENV}" 
            }
        }
   
}
    
}
