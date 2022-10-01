pipeline {
    agent any    
    environment {
        ENV_URL       = "pipeline.google.com"
        SSH_CRED      = credentials('SSH')
    }

    stages {

        stage('Perform Lint Checks') {
            steps {
                sh "env"
                sh "           
            }
        }

        stage('Do a Dry-Run') {
            steps {
                sh "env"
                sh "ansible-playbook robot-dryrun.yml -e COMPONENT=mongodb -e ENV=dev -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW}"           
            }
        }
    }
}

// SSH_CRED_USR
// SSH_CRED_PSW