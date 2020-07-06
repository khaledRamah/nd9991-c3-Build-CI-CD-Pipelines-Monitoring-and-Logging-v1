pipeline {
  agent any
  stages {
    stage('AWS Credentials') {
      steps {
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'AWSCred', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
        sh """  
               mkdir -p ~/.aws
               echo "[default]" >~/.aws/credentials
               echo "[default]" >~/.boto
               echo "aws_access_key_id = ${accessKeyVariable}" >>~/.boto
        """
        }
      }
    }
  }
}
