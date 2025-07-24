pipeline {
    agent {
        label 'slave1'
    }

    stages {
        stage('Code') {
            steps {
              git 'https://github.com/sbagavathi1911/web-app.git'
            }
        }
        stage('code-build') {
            steps {
                 sh "mvn clean package"
            }
        }
       
    }
    post{
        success{
            echo "sucess"
        }
    }
}
