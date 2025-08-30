pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo "Cloning repo..."
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "Building project..."
                sh 'echo "Compiling code..."'
                sh 'mkdir -p build && echo "Build successful at $(date)" > build/output.txt'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'echo "All tests passed!"'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying application..."
                sh 'cat build/output.txt'
            }
        }
    }
    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed!"
        }
    }
}

