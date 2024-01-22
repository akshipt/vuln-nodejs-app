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
                    def changeSets = currentBuild.changeSets

                    if (changeSets != null && !changeSets.isEmpty()) {
                        def changes = changeSets[0].items.collect { it.path }

                        if (changes.contains(modifiedFile)) {
                            echo "The file $modifiedFile has been modified."
                            // Add your further steps or actions here
                        } else {
                            echo "The file $modifiedFile has not been modified."
                            // Add alternative steps or actions here
                        }
                    } else {
                        echo "No changes found in this build."
                    }
                }
            }
        }

        // Add more stages as needed for your pipeline
    }
}
