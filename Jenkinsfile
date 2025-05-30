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
                        sh "echo "installing git""
                        sh "sudo yum install -y git httpd || echo "not installed""
                        sh "systemctl start httpd"
                        sh "systemctl enable httpd"
                        sh "systemctl status httpd"
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        sh "cp -r index.html /var/www/html/ "
                        sh "chmod -R 777 index.html"
                        }
                    }
                }
                 stage('running httpd on slave-2'){
                    agent{
                        label "slave-2"
                    }
                    steps{
                        dir('/mnt/project-workspace'){
                        sh "sudo yum install -y git httpd"
                        sh "systemctl start httpd"
                        sh "systemctl enable httpd"
                        sh "systemctl status httpd"
                        sh "git clone https://github.com/1720-swaraj/project.git"
                        sh "cp -r index.html /var/www/html/ "
                        sh "chmod -R 777 index.html"
                        }
                    }
                }
            }
        }
    }
}