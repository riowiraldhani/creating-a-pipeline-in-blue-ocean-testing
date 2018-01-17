pipeline {
  agent any
  stages {
    stage('Example Stage') {
      steps {
        echo 'Hello world!'
        echo "The value of my GitHub personal access token is $GITHUB_ACCESS_TOKEN"
        echo "The value of 'test-user-globaL' is $TEST_USER_GLOBAL"
        echo "The value of 'secret-text-globaL' is $SECRET_TEXT_GLOBAL"
        echo "The value of 'secret-file-global' is $SECRET_FILE_GLOBAL"
        withCredentials(bindings: [sshUserPrivateKey(credentialsId: 'jenkins-ssh-key-for-xyz', \
                                                   keyFileVariable: 'SSH_KEY_FOR_XYZ')]) {
          echo "The value of 'jenkins-ssh-key-for-xyz' is $SSH_KEY_FOR_XYZ"
        }
        
        withCredentials(bindings: [certificate(credentialsId: 'jenkins-certificate-for-xyz', \
                                             keystoreVariable: 'CERTIFICATE_FOR_XYZ',
                                             passwordVariable: 'test')]) {
          echo "The value of 'jenkins-certificate-for-xyz' is $CERTIFICATE_FOR_XYZ"
        }
        
        withCredentials(bindings: [sshUserPrivateKey(credentialsId: 'alex-ssh-key-global', keyFileVariable: 'ALEX_SSH_KEY_GLOBAL')]) {
          echo "The value of 'alex-ssh-key-global' is $ALEX_SSH_KEY_GLOBAL"
        }
        
        withCredentials(bindings: [certificate(credentialsId: 'certificate-global', keystoreVariable: 'CERTIFICATE_GLOBAL')]) {
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