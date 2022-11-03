pipeline {
    agent any
//   agent {
//     docker { image 'node:latest' }
//   }
  stages {
    stage('Install') {
      steps { sh 'npm install' }
    }
 
    stage('Test') {
      parallel {
        // stage('Static code analysis') {
        //     steps { sh 'npm run-script lint' }
        // }
        stage('Unit tests') {
            steps { sh 'npm run-script test -- --no-watch --no-progress --browsers=ChromeHeadlessCI' }
        }
      }
    }
 
    stage('Build') {
      steps { sh 'npm run-script build' }
    }
  }
}