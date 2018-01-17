pipeline {
  agent any
  stages {
    stage('Example Stage') {
      steps {
        echo 'Hello world!'
        echo "The value of my GitHub personal access token is $GITHUB_ACCESS_TOKEN"
        echo "The value of 'alex-username-and-password-global' is $ALEX_USERNAME_AND_PASSWORD_GLOBAL"
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
    ALEX_USERNAME_AND_PASSWORD = credentials('alex-username-and-password')
    SECRET_TEXT_GLOBAL = credentials('secret-text-global')
    SECRET_FILE_GLOBAL = credentials('secret-file-global')
  }
}