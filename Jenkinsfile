pipeline {
    agent {
        label 'built-in'
    }
    environment {
        DOCKER_IMAGE = "httpd-${env.BRANCH_NAME}"
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
                sh '''
                    docker run -itdp 80:80 --name \$DOCKER_IMAGE -v /web-site:usr/local/apache2/htdocs/ httpd
                    docker ps -a
                '''
            }
        }
    }
}
