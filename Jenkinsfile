pipeline {
  agent any
  stages {
    stage('Example Stage') {
      steps {
        echo 'Hello world!'
        echo "The value of my GitHub personal access token is $GITHUB_ACCESS_TOKEN"
        echo "The value of my GitHub personal access token is $GIT_SSH_KEY"
      }
    }
  }
  environment {
    GITHUB_ACCESS_TOKEN = credentials('github')
    GIT_SSH_KEY = credentials('jenkins-generated-ssh-key')
  }
}