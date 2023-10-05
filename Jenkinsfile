pipeline {
    agent any

    stages {
        stage('code') {
            steps {
                git credentialsId: '669d831e-4059-4743-8597-dcc31351d66f', url: 'https://github.com/sunildevops77/maven.git'
            }
        }
		stage('compile') {
            steps {
               sh 'mvn compile'
            }
        }
		stage('package') {
            steps {
                sh 'mvn package'
            }
        }
		stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '669d831e-4059-4743-8597-dcc31351d66f', path: '', url: 'http://18.60.214.92:8081/')], contextPath: 'god', war: '**/*.war'
            }
        }
    }
}
