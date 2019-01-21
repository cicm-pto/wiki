#!groovy


        properties([
            parameters([
                choice (choices:'No\nYes', description: "inovke", name: 'Invoke_Parameters'),
                choice (choices:'xTrans\nItem1,Item2\nItem2\nItem3\nItem4\nItem5\nItem6\n', description: "description here", name: 'items_list'),
                string(defaultValue: 'nothing', name: 'TEST_VAR'),
                booleanParam(defaulValue: false, name: 'Dev'),
                string (defaultValue:'xTrans,Dev,QA,PVT,PROD', description: "descriptiuon there", name: 'ENVIRONMENTS'),
                booleanParam(defaulValue: false, name: 'Test'),
                booleanParam(defaulValue: false, name: 'Stage'),
                booleanParam(defaulValue: false, name: 'Prod'),

            ])
        ])

node {
    timestamps {

        stage("parameterizing") {

                echo params.ENVIRONMENTS.split(',')
                script {
                    if ("${params.Invoke_Parameters}" == "Yes") {
                        currentBuild.result = 'ABORTED'
                        error('DRY RUN COMPLETED. JOB PARAMETERIZED.')
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
