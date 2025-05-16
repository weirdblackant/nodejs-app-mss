pipeline {
  agent any
  triggers {
    githubPush()
  }
  tools {
    git 'Default'
  }
  stages {
    stage("git_scm") {
      steps {
        git credentialsId: 'git_cred', url: 'https://github.com/weirdblackant/nodejs-app-mss.git'
      }
    }
    stage('install_dependencies') {
      steps {
        sh "npm install" 
      }
    }
    stage('build_app') {
      steps {
	sh "npm start"
      }
    }
  }
}

