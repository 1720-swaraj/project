pipeline {
    agent {
        label 'built-in'
    }
    stages {
        stage('stage-1') {
            dir('/mnt/') {
                steps {
                    sh 'echo "master branch"'
                    git url: 'https://github.com/1720-swaraj/project.git .'
                }
            }
        }
    }
}
