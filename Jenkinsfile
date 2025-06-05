pipeline{
    agent{
        label 'built-in'
    }
    tools{
        maven 'install-maven'
    }
    stages{
        stage('stage-1'){
            steps{
                cleanWs()
                sh 'echo "project clonning"'
                git url: 'https://github.com/1720-swaraj/project.git', branch: 'master'
            }
        }
    }
}