pipeline {
    agent any

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
                withCredentials([usernamePassword(credentialsId: 'docker_id', passwordVariable: 'DOCKER_REGISTRY_PWD', usernameVariable: 'DOCKER_REGISTRY_USER')]) {
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