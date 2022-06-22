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
                nodejs('nodejs') {
                    sh 'node --vesion'
                }
            }
        }
    }
}
