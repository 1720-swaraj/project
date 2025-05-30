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
                        sh "chmod -R 777 /mnt"
                        sh "yum install git -y"
                        sh "yum install httpd -y"
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
                        sh "chmod -R 777 /mnt"    
                        sh "yum install git -y"
                        sh "yum install httpd -y"
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