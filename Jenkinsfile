pipeline {
    agent{
    label 'built-in'
        customWorkspace '/mnt'
    }
    stages{
        stage('stage-1'){
              steps{
                  sh 'chmod -R 777 /mnt'
                  sh 'echo "cloning project on master"'
                  git url: 'https://github.com/1720-swaraj/project.git', branch: 'master'
              }
        }
    }
}
