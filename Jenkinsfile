pipeline {
agent {
label '24thdevops'
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
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
   
}
    
}
