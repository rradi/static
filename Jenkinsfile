pipeline{
        agent any
        stages {
            stage('Lint HTML'){
                steps {
                    sh 'tidy -q -e *.html'
                }
            }
            stage('Upload to AWS') {
                steps {
                    retry(3){
                        withAWS(region:'us-west-2', credentials:'admin'){
                        s3Upload(file:'index.html', bucket:'rradi-udacity-jenkins', path:'')
                    }                             
                }
            }
        }
    }
}
