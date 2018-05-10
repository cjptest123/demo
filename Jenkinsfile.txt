pipeline {
    agent { label 'winslave' }

    stages {
        stage('Build') {
            steps {
                bat 'dotnet clean'
                bat 'dotnet build'
            }
        }
}
}