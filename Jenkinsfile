pipeline {
    agent {
        label 'built-in'
    }
    stages {
        stage('stage-1') {
                steps {
                    dir('/mnt/') {
                    sh 'echo "master branch"'
                    git url: 'https://github.com/1720-swaraj/project.git .', branch: 'master'
                    }
                }
        }
    }
}
