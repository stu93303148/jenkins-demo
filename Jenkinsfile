pipeline {
  environment {
    registry = "stu93303148/jenkins-demo"
    registryCredential = 'dockerhub_credentials'
    dockerImage = ''
    githubCredential = 'git_credentials'
    githubBranch = 'main'
    githubURL = 'https://github.com/stu93303148/jenkins-demo.git'
  }
  agent any
  stages {
    stage('Github Clone') {
      steps {
        echo "1.Clone Stage"
        git credentialsId: githubCredential, url: githubURL, branch: githubBranch
        script {
            build_tag = sh(returnStdout: true, script: 'git rev-parse --short HEAD').trim()
        }
      }
    }
    stage('Image Build') {
      steps {
        echo "2.Build Stage - ${build_tag}"
        script {
          dockerImage = docker.build registry + ":$build_tag"
        }
      }
    }
    stage('Image Deploy DockerHub') {
      steps {
        echo "3. Deploy Stage"
      }
    }
  }
}
