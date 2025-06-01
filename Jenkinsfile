pipeline{
    agent{
        label 'built-in'
    }
    tools{
        git 'install-git'
    }
    stages{
        stage('stage-1'){
            steps{
                sh 'git --version'
            }
        }
    }
}