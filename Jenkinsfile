properties([parameters([choice(choices: ['account-service', 'customer-service', 'discovery-service', 'gateway-service', 'zipkin-service'], description: 'these are the parametrized services', name: 'BUILD_ENV')]), pipelineTriggers([githubPush()])])

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
        stage('Build') {
            steps {
                
                sh "cd /home/ubuntu/workspace/jenkinspipeline/account-service; mvn clean install "
                echo "Will deploy to ${BUILD_ENV}"
               echo "Will deploy to ${params.BUILD_ENV}" 
            }
        }
   
}
    
}
