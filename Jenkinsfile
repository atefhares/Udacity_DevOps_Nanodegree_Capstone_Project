pipeline {
    agent any

    stages {
        stage('TESTING') {
            steps {
               sh "python3 PythonApp/tests/test.py"
            }
        }

        stage('DOCKERIZING') {
            steps {
                sh "docker build --tag=simple_python_app ."
            }
        }

        stage('PUSHING') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker_id', passwordVariable: 'DOCKER_REGISTRY_PWD', usernameVariable: 'DOCKER_REGISTRY_USER')]) {
                  sh 'docker login -u=$DOCKER_REGISTRY_USER -p=$DOCKER_REGISTRY_PWD'
                  sh 'docker tag simple_python_app atefhares/simple_python_app:latest'
                  sh "docker push atefhares/simple_python_app"
                }
            } 
        }

        stage('Build infrastructure for the app') {
            steps {
                withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'aws-key', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh '/usr/local/bin/aws s3 ls'
                //    sh './cloudformation/create.sh AtefUdacityCapstoneStack cloudformation/infrastructure.yml cloudformation/params.json'
                }
            }
        }

        //  stage('Deploy the app') {
        //     steps {
                
        //     }
        // }
    }
}