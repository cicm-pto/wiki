#!groovy

node {
    timestamps {
        try {
            stage('Initialization') {
                def name = "hal"
                assert name : 'Name should be defined'
                echo 'Reading from git'
            }

            stage('Build') { 
                echo 'build stage step1'
                echo 'build stage step2'
            }

            stage('Test') { 
                echo 'Test Stage step 1'
            }

            stage('Deploy') {
                echo 'Deploy Stage step 1'
            }
        }
        catch (AssertionError e) {
            currentBuild.result = 'ABORTED'
            echo "Build is now ABORTED.\n${e}"
        } 
    }
}
