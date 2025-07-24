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
        stage('build') {
            steps {
                 sh "mvn clean package"
            }
        }
        stage('artifact') {
            steps {
                     nexusArtifactUploader artifacts: [[artifactId: 'mywebapps', classifier: '', file: 'target/myweb-8.6.5', type: '.war']], credentialsId: 'admin', groupId: 'in.javahome', nexusUrl: '52.210.224.48:808', nexusVersion: 'nexus3', protocol: 'http', repository: 'devil', version: '8.6.5'
                   }
             }
    }
    post{
        success {
            echo "sucess"
        }
    }
}
