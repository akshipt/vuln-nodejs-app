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
                    
                    def changeSet = currentBuild.changeSets.poll()

                    if (changeSet != null) {
                        def changes = changeSet.items.collect { it.path }

                        if (changes.contains(modifiedFile)) {
                            echo "The file $modifiedFile has been modified."
                            // Add action
                        } else {
                            echo "The file $modifiedFile has not been modified."
                            // Add action
                        }
                    } else {
                        echo "No changes found in this build."
                    }
                }
            }
        }

    }
}
