pipeline {
    agent any
    stages {
        stage('test') {
            steps {
               sh "python3 PythonApp/tests/test.py"
            }
        }

        stage('Build docker image') {
            // steps {
                // sh "docker-compose -f challenge_1/docker-compose.yaml up -d"
            // }
        }

        stage('Push docker image to DockerHub') {
            // steps {
                
            // }
        }

        stage('Build infrastructure for the app') {
            // steps {
                
            // }
        }

        stage('Deploy the app') {
            // steps {
                
            // }
        }
    }
}