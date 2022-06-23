properties([pipelineTriggers([githubPush()])])

pipeline {
    agent {
        label 'test'
    }
    tools {
        nodejs 'nodejs'
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('Prepare') {
            steps {
                sh 'sudo apt update -y'
                sh 'node --version'
            }
        }
        stage('Show Parameters') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
        stage('Run stage on condition') {
            when() {
                allOf {
                    environment name: 'TOGGLE', value: 'true'
                }
            }
            steps {
                sh 'npm vi'
                sh 'npm run dev'
            }
        }
    }
}
