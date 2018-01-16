pipeline {
  agent any
  stages {
    stage('Example Stage') {
      steps {
        echo 'Hello world!'
        echo 'The value of my GitHub personal access token is $GITHUB_ACCESS_TOKEN'
      }
    }
  }
  environment {
    GITHUB_ACCESS_TOKEN = credentials('github')
  }
}