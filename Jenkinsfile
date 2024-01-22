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
                    def changedFiles = sh(script: 'git diff --name-only $CHANGE_ID $CHANGE_TARGET', returnStdout: true)
                    echo "Changed files: ${changedFiles}"
                }
            }
        }

    }

}
