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
                        dir('slave-1-workspace'){
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
                 stage('slave-2'){
                    agent{
                        label "slave-2"
                    }
                    steps{
                        dir('slave-2-workspace'){    
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
            }
        }
    }
}