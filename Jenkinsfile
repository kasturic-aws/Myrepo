pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out code from the repository
                checkout scm
            }
        }

        stage('Pull Git Content') {
            steps {
                script {
                    def gitContentFolder = 'my_git_content'
                    // Create the directory if it doesn't exist
                    sh "mkdir -p $gitContentFolder"
                    dir(gitContentFolder) {
                        // Clean the directory before pulling
                        sh "rm -rf ./*"
                        // Clone the repository to the specified folder
                        sh "git clone --branch develop --single-branch ${env.GIT_URL} ."
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
