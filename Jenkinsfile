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
    stage('Clone') {
      steps {
        echo "1.Clone Stage"
        git credentialsId: githubCredential, url: githubURL, branch: githubBranch
        script {
            build_tag = sh(returnStdout: true, script: 'git rev-parse --short HEAD').trim()
        }
      }
    }
    stage('Test') {
      steps {
        echo "2.Test Stage - SKIP"
      }
    }
    stage('Build') {
      steps {
        echo "3.Build Stage - ${build_tag}"
        script {
          dockerImage = docker.build registry + ":$build_tag"
        }
      }
    }
    stage('Deploy') {
      steps {
        echo "4. Deploy Stage"
      }
    }
  }
}
