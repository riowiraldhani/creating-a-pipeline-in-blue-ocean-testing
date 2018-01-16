pipeline {
  agent any
  stages {
    stage('Example Stage') {
      steps {
        echo 'Hello world!'
        echo "The value of my GitHub personal access token is $GITHUB_ACCESS_TOKEN"
        echo "The value of 'test-user-globaL' is $TEST_USER_GLOBAL"
        echo "The value of 'secret-text-globaL' is $SECRET_TEXT_GLOBAL"
        echo "The value of 'secret-file-globaL' is $SECRET_FILE_GLOBAL"
        withCredentials(bindings: [certificate(aliasVariable: '', credentialsId: 'certificate-global', keystoreVariable: 'CERTIFICATE_GLOBAL', passwordVariable: 'test')]) {
          echo "The value of 'certificate-global' is $CERTIFICATE_GLOBAL"
        }
        
      }
    }
  }
  environment {
    GITHUB_ACCESS_TOKEN = credentials('github')
    TEST_USER_GLOBAL = credentials('test-user-global')
    SECRET_TEXT_GLOBAL = credentials('secret-text-global')
    SECRET_FILE_GLOBAL = credentials('secret-file-global')
  }
}