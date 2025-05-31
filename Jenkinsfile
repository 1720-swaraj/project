pipeline{
agent{
label 'built-in'
}
tools{
git 'git-latest'
}
stages{
stage('parallel-stage'){
parallel{
stage('slave-1'){
agent{
label "slave-1"
}
tools{
git 'git-latest'
}
steps{
dir('/project/gitfiles'){
sh 'echo "Running cleanWs in workspace: $WORKSPACE"'
cleanWs()
sh 'echo "running pwd"'
sh 'pwd'
sh 'rm -rf *'
sh "git clone https://github.com/1720-swaraj/project.git"
}
}
}
stage('slave-2'){
agent{
label "slave-2"
}
tools{
git 'git-latest'
}
steps{
dir('/project/gitfiles'){
sh 'echo "Running cleanWs in workspace: $WORKSPACE"'
cleanWs()
sh 'echo "running pwd"'
sh 'pwd'
sh 'rm -rf *'
sh "git clone https://github.com/1720-swaraj/project.git"
}
}
}
}
}
}
}