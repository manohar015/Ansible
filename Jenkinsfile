pipeline {
    agent any    
    environment {
        ENV_URL       = "pipeline.google.com"
        SSH_CRED      = credentials('SSH')
    }
 
   triggers { pollSCM('*/2 * * * *') }

    tools {
        maven 'maven-3.8.5' 
    }
   
   parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        // choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        // password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Hai') {
            steps {
                sh "echo ${ENV_URL} "  
                    
            }
        }
        stage('Hello') {
            when { branch 'master' }
            environment {
                ENV_URL = "stage.google.com"
            }
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                 sh "echo hai"  
                 sh "echo Environment URL is ${ENV_URL}"
                 sh "env" 
                 sh "echo I will be running maven command"
                 sh "mvn -v"
            }
        }
    }
}


// Environment variables for SSH UserName & Password
// SSH_CRED_USR
// SSH_CRED_PSW
// Added some commits 
// Demonstrating the PollSCM  : 19 

