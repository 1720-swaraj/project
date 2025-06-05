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
              steps{
                  withCredentials([[
                      $class: 'AmazonWebServicesCredentialsBinding',
                      credentialsId: 'aws-jenkins-creds'
                  ]]){
                      sh ''' 
                          aws s3 cp s3://build-tools-files/artifact/apache-maven-3.9.9-bin.zip /mnt/build-tools
                      '''
                  }
              }
        }
        // stage('stage-3'){
        //     agent{
        //         label 'slave'
        //     }
        //     tools{
        //         maven 'install-maven'
        //     }
        //     steps{
        //         dir('/mnt/slave'){
        //              cleanWs()
        //              sh 'echo "installing git and maven on slave"'
        //         }
               
        //     }
        }
    }
}
