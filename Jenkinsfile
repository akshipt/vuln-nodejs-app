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
                    def changes = []

                    // Iterate through all changesets
                    currentBuild.changeSets.each { changeSet ->
                        changes.addAll(changeSet.items.collect { it.path })
                    }

                    if (changes.contains(modifiedFile)) {
                        echo "The file $modifiedFile has been modified."
                        // Add your further steps or actions here
                    } else {
                        echo "The file $modifiedFile has not been modified."
                        // Add alternative steps or actions here
                    }
                }
            }
        }

        // Add more stages as needed for your pipeline
    }
}
