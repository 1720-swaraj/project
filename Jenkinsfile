pipeline{
    agent none
    stages{
        stage('parallel-stage'){
            parallel{
                stage('slave-1'){
                    agent{
                        label "slave-1"
                    }
                    steps{
                        dir('project-workspace'){
                        cleanWs()
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
                 stage('slave-2'){
                    agent{
                        label "slave-2"
                    }
                    steps{
                        dir('project-workspace'){
                        cleanWs()
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
            }
        }
    }
}