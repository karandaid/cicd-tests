pipeline {
    agent {
        label 'test'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                script {
                    sh 'ls -lrt'
                }
            }
        }
        stage('NodeJS') {
            steps {
                sh 'node --version'
            }
        }
    }
}
