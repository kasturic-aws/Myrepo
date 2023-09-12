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
                sh """
                mkdir -p my_git_content
                cd my_git_content
                git init
                git remote add origin ${env.GIT_URL}
                git fetch --depth 1 origin develop
                git checkout develop
                """
            }
        }

        // Add more stages for your pipeline as needed
    }

    post {
        always {
            // Clean up, notify, or perform any other post-pipeline tasks
        }
    }
}
