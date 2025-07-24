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

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Artifact Upload') {
            steps {
                nexusArtifactUploader(
                    artifacts: [[
                        artifactId: 'mywebapps',
                        classifier: '',
                        file: 'target/myweb-8.6.5.war',
                        type: 'war'
                    ]],
                    credentialsId: 'admin',
                    groupId: 'in.javahome',
                    nexusUrl: '52.210.224.48:8081',
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    repository: 'devil',
                    version: '8.6.5'
                )
            }
        }
    }

    post {
        success {
            echo 'Build and artifact upload successful!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

