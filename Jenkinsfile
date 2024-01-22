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
                    def changedFiles = sh(script: "git diff --name-only ${GIT_COMMIT} ${GIT_PREVIOUS_COMMIT}", returnStdout: true).trim()
		    echo "Changed files: ${changedFiles}"
		    def filesArray = changedFiles.split("\n")
                    echo "New Changed Files: ${filesArray}"
		    def filetocheck = "package.json"
 		    if (filesArray.contains(filetocheck)){
			echo "package.json Modified"
			sh "cdxgen --api-key odt_gZohq6E4J0h63dS66umB3iK3szP0mx84 --server-url http://localhost:8082"
		} else {
			echo "Not modified"		
}
                }
            }
        }

        // Add more stages as needed for your build process
    }

}
