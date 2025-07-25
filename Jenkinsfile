pipeline {
    agent {
        label '  '
    }

    stages {
        stage('Code') {
            steps {
                git 'https://github.com/sbagavathi1911/web-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('artifact') {
            steps {
               
            }
        }

        stage('deploy') {
            steps {

            }
        }
    }
    post {
        success {
            echo 'success'
    }
}
}
