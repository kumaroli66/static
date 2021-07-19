pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e index.html'
            }
        }
        stage('Upload to AWS') {
            steps {
		    sh 'echo "Hello World with AWS creds"'
		    withAWS(profile:'default', region:'us-east-2') {
    			s3Upload(file:'index.html', bucket:'koli-test-bucket', path:'index.html')
		    }
            }
        }
    }
}
