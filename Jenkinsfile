pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check File Modification') {
            steps {
                script {
                    def modifiedFile = 'package.json'
                    def changes = scm.diffIncludes()

                    if (changes.contains(modifiedFile)) {
                        echo "The file $modifiedFile has been modified."
                        // Add action
                    } else {
                        echo "The file $modifiedFile has not been modified."
                        // Add action
                    }
                }
            }
        }

    }
}
