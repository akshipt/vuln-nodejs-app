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
                    def changes = script {
                        return checkout([$class: 'GitSCM']).pollingBaseline().polling().changes
                    }
                    
                    def hasPackageJsonChanged = changes.any { it.filePath.endsWith('package.json') }

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
