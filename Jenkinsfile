pipeline{
    agent none
    stages{
        stage('parallel-stage'){
            parallel{
                stage('slave-1'){
                    agent{
                        label "jenkins-slave-1"
                    }
                    steps{
                        dir('slave-1-workspace'){
                            cleanWs()
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
                 stage('slave-2'){
                    agent{
                        label "jenkins-slave-2"
                    }
                    steps{
                        dir('slave-2-workspace'){
                            cleanWs()
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
            }
        }
    }
}