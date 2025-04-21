pipeline {
agent any
stages {
stage('Checkout') {
steps {
git branch: 'master', url: ' https://github.com/TEEYUCHEN/practical_8_github_actions.git'
}
}
stage('Build') {
steps { powershell 'gradle clean build'}
}
stage('Test') {
steps { powershell 'gradle test'}
}
stage('Deploy') {
steps { powershell 'java -jar build/libs/hello-world-javaV1.jar'}
}
}
post {
always {
echo 'Cleaning up workspace'
deleteDir() // Clean up the workspace after the build
}
success {
echo 'Build succeeded!!!'
// You could add notification steps here
}
failure {
echo 'Build failed!'
// You could add notification steps here
}
}
}
