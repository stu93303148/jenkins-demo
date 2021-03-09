node {
  stage('Clone') {
    echo "1.Clone Stage"
    git url: "https://github.com/stu93303148/jenkins-demo.git"
  }
  stage('Test') {
    echo "2.Test Stage"
  }
  stage('Build') {
    echo "3.Build Stage"
    sh "docker build -t stu93303148/jenkins-demo:${build_tag} ."
  }
  stage('Deploy') {
    echo "4. Deploy Stage"
  }
}
