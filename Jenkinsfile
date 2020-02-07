pipeline {
     agent any
     stages {   
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-west-2',credentials:"aws-static") {
                  sh 'echo "Uploading content with AWS credentials"'
                      s3Upload(file:'index.html', bucket:'rradi-udacity-jenkins', path:'index.html')
                  }
              }
         }
     }
}
