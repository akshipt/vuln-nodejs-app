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
                    sh(script: 'printenv')
		    //def changedFiles = sh(script: 'git diff --name-only origin/master...HEAD -- package.json', returnStdout: true).trim()
                    //echo "Changed files: ${changedFiles}"
                }
            }
        }

        // Add more stages as needed for your build process
    }

}
