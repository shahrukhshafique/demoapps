pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Hello this is Build stage'
                sh 'docker buil ./HelloWorld/
            }
        }
        stage('Test') {
            steps {
                echo 'Hello this is test stage'
            }
        }
        stage('deploy') {
            steps {
                echo 'Hello this is deploy stage'
            }
        }
    }
}
