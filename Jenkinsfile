pipeline {
    agent {
        label 'built-in'
    }
    environment {
        DOCKER_CONTAINER = "httpd-${env.BRANCH_NAME}"
        DOCKER_IMAGE = 'httpd:latest'
    }
    stages {
        stage('checkout') {
            steps {
                cleanWs()
                checkout scm
            }
        }
        stage('copy') {
            steps {
                sh 'mkdir -p web-site'
                sh 'cp index.html web-site'
            }
        }
        stage('build') {
            steps {
                script {
                    def isDockerPresent = sh(script: "docker images -q ${env.DOCKER_IMAGE}", returnStdout: true)
                    if (isDockerPresent) {
                        sh "docker rmi -f ${env.DOCKER_IMAGE}"
                    }
                        sh '''
                    docker run -itdp 80:80 --name \$DOCKER_CONTAINER -v \$WORKSPACE/web-site:/usr/local/apache2/htdocs/ httpd
                    docker ps -a
                '''
                }
            }
        }
    }
}
