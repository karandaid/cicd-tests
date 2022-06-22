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
                nodejs(nodeJSInstallationName: 'Node 6.x', configId: '<config-file-provider-id>') {
                    sh 'npm config ls'
                }
            }
        }
    }
}
