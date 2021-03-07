pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Hello this is Build stage'
                sh '''
                sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
                sudo yum install dotnet-sdk-5.0
                sudo yum install dotnet-runtime-5.0
                '''
                dotnetRestore sdk: 'DOTNET-5.0', workDirectory: './HelloWorld/'
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
