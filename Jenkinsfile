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
                properties([
  parameters([
    string(name: 'BUILD_ENV', defaultValue: 'account-service''customer-service''discovery-service''gateway-service''zipkin-service', description: 'The target environment', )
   ])
])
                echo "Will deploy to ${BUILD_ENV}"
               echo "Will deploy to ${params.BUILD_ENV}" 
            }
        }
   
}
    
}
