pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static', region: 'eu-central-1') {
          s3Upload(file:'index.html', bucket:'jenkins-bucket-project-4', path:'index.html')
        }
      }
    }
  }
}
