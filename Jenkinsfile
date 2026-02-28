pipeline {
    // agent {
    //     docker {
    //         image 'python:3.9'
    //     }
    // }
    agent any
    
    stages {
        stage('Initialize') {
            steps {
                echo '🚀 Starting the DevOps Pipeline...'
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Git Branch: ${env.BRANCH_NAME ?: 'main'}"
                sh '''
                    echo "================================"
                    echo "Running in Docker Agent:"
                    echo "Container: $(hostname)"
                    echo "Python: $(python --version)"
                    echo "================================"
                '''
            }
        }
        
        stage('Build') {
            steps {
                echo '🛠 Building the application...'
                sh 'echo "Simulating Maven Build..." && sleep 2'
                sh 'docker ps'
            }
        }
        
        stage('Test') {
            steps {
                echo '🧪 Running Unit Tests...'
                sh 'echo "Simulating Tests..." && sleep 2'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to Docker Hub...'
                sh 'echo "Image Pushed Successfully"'
            }
        }
    }
    
    post {
        always {
            echo '🧹 Cleaning up workspace...'
            echo 'Docker container will be automatically destroyed'
        }
        success {
            echo 'Success: Pipeline completed in Docker agent!'
        }
        failure {
            echo 'Danger: The build failed!'
        }
    }
}