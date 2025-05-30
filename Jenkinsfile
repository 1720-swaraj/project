pipeline{
    agent none
    stages{
        stage('parallel-stage'){
            parallel{
                stage('running httpd on slave-1'){
                    agent{
                        label "slave-1"
                    }
                    steps{
                        dir('/mnt/project-workspace'){
                        sh 'sudo chmod -R 777 /mnt'    
                        sh 'echo "slave-1 working directory is $WORKSPACE"'
                        cleanWs()
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
                 stage('running httpd on slave-2'){
                    agent{
                        label "slave-2"
                    }
                    steps{
                        dir('/mnt/project-workspace'){
                        sh 'sudo chmod -R 777 /mnt'
                        sh 'echo "slave-2 working directory is $WORKSPACE"'
                        cleanWs()
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        }
                    }
                }
            }
        }
    }
}