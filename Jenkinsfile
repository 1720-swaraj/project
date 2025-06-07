pipeline{
    agent{
        label 'built-in'
    }
    environment{
        DOCKER_IMAGE = " httpd-${env.BRANCH_NAME}"
    }
    stages{
        stage('checkout'){
            steps{
                cleanWs()
                checkout scm
            }
        }
        stage('build'){
            steps{
                sh 'env'
            }
        }
    }
}