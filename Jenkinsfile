pipeline {
    agent {
        label 'built-in'
    }
    tools{
        git 'git-install'
    }
    stages {
        stage('stage-1') {
                steps {
                    dir('/mnt/master') {
                    sh 'echo "master branch"'
                    git url: 'https://github.com/1720-swaraj/project.git', branch: 'master'
                    }
                }
        }
    }
}
