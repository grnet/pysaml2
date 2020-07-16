pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile.build'
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'pytest tests/test_51_client.py::TestClient::test_create_auth_request_requested_attributes'
            }
        }
    }
}
