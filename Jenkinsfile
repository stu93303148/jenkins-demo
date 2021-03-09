node {
  stage('Clone') {
    echo "1.Clone Stage"
    git credentialsId: "git_credentials", url: "https://github.com/stu93303148/jenkins-demo.git", branch: "main"
  }
  stage('Test') {
    echo "2.Test Stage"
  }
  stage('Build') {
    echo "3.Build Stage"
  }
  stage('Deploy') {
    echo "4. Deploy Stage"
  }
}
