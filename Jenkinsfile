pipeline {
    agent any    
    environment {
        ENV_URL       = "pipeline.google.com"
        SSH_CRED      = credentials('SSH')
    }

    stages {
        stage('Do a Dry-Run') {
            steps {
                sh "echo ${ENV_URL} "  
                    
            }
        }
    }
}
