pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the code from Git
                    checkout scm
                }
            }
        }

        stage('Identify Changed Files') {
            steps {
                script {
                    // Run git command to identify changed files
                    def changedFiles = sh(script: 'git diff --name-only origin/master...HEAD', returnStdout: true).trim()
                    echo "Changed files: ${changedFiles}"
                }
            }
        }

        // Add more stages as needed for your build process
    }

    post {
        always {
            // Clean up or perform any post-build actions
        }
    }
}
