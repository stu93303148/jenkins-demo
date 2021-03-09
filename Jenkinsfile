node {
  stage('Clone') {
    echo "1.Clone Stage"
    git credentialsId: "git_credentials", url: "https://github.com/stu93303148/jenkins-demo.git", branch: "main"
    script {
        build_tag = sh(returnStdout: true, script: 'git rev-parse --short HEAD').trim()
    }
  }
  stage('Test') {
    echo "2.Test Stage - SKIP"
  }
  stage('Build') {
    echo "3.Build Stage - ${build_tag}"
    sh "docker build -t stu93303148/jenkins-demo:${build_tag} ."
  }
  stage('Deploy') {
    echo "4. Deploy Stage"
  }
}
