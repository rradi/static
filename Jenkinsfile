pipeline {
     agent any
     stages {   
         stage('Lint HTML') {
              steps {
                  sh 'echo "HTML lint test"'
                  sh 'tidy -q -e *.html'
              }
         }
          
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-west-2',credentials:'admin') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'rradi-udacity-jenkins')
                  }
              }
         }
     }
}
