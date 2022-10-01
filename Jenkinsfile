pipeline {
    agent any    
    environment {
        ENV_URL       = "pipeline.google.com"
        SSH_CRED      = credentials('SSH')
    }

    stages {
        stage('Do a Dry-Run') {
            steps {
                sh "ansible-playbook robot-dryrun.yml -e COMPONENT=mongodb -e ENV=dev -e ansible_user=centos -e ansible_password=DevOps321"  
                    
            }
        }
    }
}

// SSH_CRED_USR
// SSH_CRED_PSW