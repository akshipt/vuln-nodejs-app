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

        stage('Check Package.json Changes') {
            steps {
                script {
                    // Check if package.json has changed
                    def changes = checkout([$class: 'GitSCM']).pollingBaseline().polling().getBuildCommits()
                    def hasPackageJsonChanged = changes.any { it.comment.contains('package.json') }

                    if (hasPackageJsonChanged) {
                        echo 'Package.json has changed in the current push.'
                        // Add your further steps here
                    } else {
                        echo 'Package.json has not changed in the current push.'
                        // Add your alternative steps here
                    }
                }
            }
        }
    }
}
