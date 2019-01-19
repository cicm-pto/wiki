#!groovy

        properties([
            parameters([
                choice (choices:'Yes\nNo', description: "inovke", name: 'Invoke_Parameters'),
                string(defaultValue: 'nothing', name: 'TEST_VAR'),
                booleanParam(defaulValue: false, name: 'Dev'),
                booleanParam(defaulValue: false, name: 'Test'),
                booleanParam(defaulValue: false, name: 'Stage'),
                booleanParam(defaulValue: false, name: 'Prod'),
                string(defaultValue: 'nothing', name: 'TEST_VAR2'),
                booleanParam(defaulValue: false, name: 'Dev2'),
                booleanParam(defaulValue: false, name: 'Test2'),
                booleanParam(defaulValue: false, name: 'Stage2'),
                booleanParam(defaulValue: false, name: 'Prod2')
            ])
        ])

node {
    timestamps {

        stage("parameterizing") {
            steps {
                script {
                    if ("${params.Invoke_Parameters}" == "Yes") {
                        currentBuild.result = 'ABORTED'
                        error('DRY RUN COMPLETED. JOB PARAMETERIZED.')
                    }
                }
            }
        }

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
