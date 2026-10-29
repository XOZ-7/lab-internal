pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Build Docker Image"
                bat "docker build -t myphythonflaskapp ."
            }
        }
        stage('Run') {
            steps {
                echo "Run application in Docker container"
                bat "docker run -d -p 3000:5000 --name mycontainer myphythonflaskapp"
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}