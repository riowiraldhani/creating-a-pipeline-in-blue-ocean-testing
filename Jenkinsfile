pipeline {
  agent any
  stages {
    stage('Example Stage') {
      steps {
        echo 'Hello world!'
        echo "The value of my GitHub personal access token is $GITHUB_ACCESS_TOKEN"
        echo "The value of 'alex-ssh-key-global' is $TEST_USER_GLOBAL"
        echo "The value of 'alex-ssh-key-global' is $ALEX_SSH_KEY_GLOBAL"
      }
    }
  }
  environment {
    GITHUB_ACCESS_TOKEN = credentials('github')
    TEST_USER_GLOBAL = credentials('test-user-global')
  }
}