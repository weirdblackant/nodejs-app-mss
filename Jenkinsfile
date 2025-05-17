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
	nodejs(nodeJSInstallationName: 'nodejs22.40.0')
        sh "npm install" 
      }
    }
    stage('build_app') {
      steps {
	nodejs(nodeJSInstallationName: 'nodejs22.40.0')
	sh "npm start"
      }
    }
  }
}
