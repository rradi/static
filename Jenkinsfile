pipeline {
     agent any
     stages {
          stage('Lint HTML.'){
               steps {
                    sh "tidy -q -e *.html"
               }
          }
          stage('Upload to AWS') {
               steps {
                    withAWS(region:'us-west-2',credentials:'aws-static') {
                         sh 'echo "Uploading content with AWS credentials"'
                         s3Upload(file:'index.html', bucket:'rradi-udacity-jenkins', path:'index.html')
                    }
               }
          }
     }
}
