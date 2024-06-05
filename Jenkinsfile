pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('1') 
        DOCKER_HUB_USERNAME = 'aghaali1'
    }

    stages {
        stage('Checkout 1129') {
            steps {
                git 'https://github.com/NUCESFAST/scd-final-lab-exam-aleedurrani.git'
            }
        }

        stage('Build and Push Auth Image 1129') {
            steps {
                script {
                    dockerBuildAndPush('Auth')
                }
            }
        }

        stage('Build and Push Classroom Image 1129') {
            steps {
                script {
                    dockerBuildAndPush('Classrooms')
                }
            }
        }

        stage('Build and Push Event-Bus Image 1129') {
            steps {
                script {
                    dockerBuildAndPush('event-bus')
                }
            }
        }

        stage('Build and Push Post Image 1129') {
            steps {
                script {
                    dockerBuildAndPush('Post')
                }
            }
        }

        stage('Build and Push Client Image 1129') {
            steps {
                script {
                    dockerBuildAndPush('client')
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}

def dockerBuildAndPush(serviceName) {
    def imageName = "${DOCKER_HUB_USERNAME}/${serviceName}:latest"
    docker.withRegistry('https://index.docker.io/v1/', DOCKER_HUB_CREDENTIALS) {
        docker.build(imageName, "./${serviceName}").push()
    }
}
