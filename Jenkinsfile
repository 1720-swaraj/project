pipeline {
    agent{
        label 'built-in'
    }
    stages{
        stage('stage-1'){
              steps{
                  cleanWs()
                  sh 'echo "cloning project on master"'
                  git url: 'https://github.com/1720-swaraj/project.git', branch: 'master'
              }
        }
        stage('stage-2'){
            label{
                label 'slave'
            }
            tools{
                maven 'install-maven'
                git 'install-git'
            }
            steps{
                dir('/slave'){
                     sh 'echo "installing git and maven on slave"'
                }
               
            }
        }
    }
}
