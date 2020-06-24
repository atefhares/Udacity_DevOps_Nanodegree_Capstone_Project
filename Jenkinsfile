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
                sh "docker build --tag=simple_python_app ."
            }
        }

        stage('Push docker image to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker_id', passwordVariable: 'DOCKER_REGISTRY_PWD', usernameVariable: 'DOCKER_REGISTRY_USER')]) {
                  sh 'docker login -u=$DOCKER_REGISTRY_USER -p=$DOCKER_REGISTRY_PWD'
                  sh "docker push atefhares/simple_python_app:latest"
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