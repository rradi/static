pipeline {
	agent any
	stages {
		stage ('Upload to AWS') {
			steps {
				withAWS(region:'us-west-2',credentials:'admin') {
					s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'rradi-udacity-jenkins')
				}
			}
		}
	}
}
