pipeline {
    agent any
    environment {
        registry = "atefhares/simple_python_app"
        registryCredential = 'docker_id'
        dockerImage = ''
    }

    stages {
        stage('unit testing') {
            steps {
               sh "python3 PythonApp/tests/test.py"
            }
        }

        stage('Build docker image') {
            steps {
                sh "docker build --tag=atefhares/simple_python_app:latest ."
            }
        }

        stage('Push docker image to DockerHub') {
            steps {
                docker.withRegistry( '', registryCredential ) {
                    sh "docker push atefhares/simple_python_app"
                }
            }
        }

        // stage('Build infrastructure for the app') {
        //     steps {
                
        //     }
        // }

        //  stage('Deploy the app') {
        //     steps {
                
        //     }
        // }
    }
}