pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static', region: 'eu-central-1') {
          s3Upload(file:'index.html', bucket:'jenkins-bucket-project-4', path:'index.html')
        }
      }
    }
  }
}
