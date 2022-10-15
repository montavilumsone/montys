pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/montavilumsone/montys.git']]])
            }
        }
        stage('Build') {
            steps {
              sh 'sudo ansible-playbook playbook.yaml --extra-vars "text=${SHARK}"'
            }
        }
        
    }
}
