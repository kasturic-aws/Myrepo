pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                checkout scm
            }
        }

        stage('Pull Git Content') {
            steps {
                script {
                    def gitContentFolder = 'my_git_content'
                    dir(gitContentFolder) {
                        // Clone the repository to the specified folder
                        sh "git clone --branch develop --single-branch ${env.BUILD_URL}.git ."
                    }
                }
            }
        }

        // Add more stages for your pipeline as needed
    }
    post {
        always {
            // Clean up, notify, or perform any other post-pipeline tasks
            echo "Hello, World!"  // This is a simple example step
        }
    }
}
