pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile.build'
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'pytest --deselect tests/test_51_client.py::TestClient::test_create_auth_request_requested_attributes'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
        success {
            script{
                if ( env.BRANCH_NAME == 'eIDAS' ) {
                    build job: '/IDENTITY/devs%2Fidentity%2Fsatosa/eIDAS', propagate: false
                }
            }
        }
    }
}
