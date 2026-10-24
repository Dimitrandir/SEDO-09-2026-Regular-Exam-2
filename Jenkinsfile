pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Restore') {
            steps {
                sh 'dotnet restore Homies.sln'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build Homies.sln --no-restore --configuration Release'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test Homies.sln --no-build --configuration Release'
            }
        }
    }
}
