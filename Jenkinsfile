#!groovy

node {
    stages {
        stage('Initialization') {

            options {
                skipDefaultCheckout
                timestamps
            }

            parameters {
                text(name: 'DEPLOY_TEXT', defaultValue: 'One\nTwo\nThree\n', description: '')
                choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
            }

            try {

                steps {
                    echo "DEPLOY_TEXT: ${params.DEPLOY_TEXT}"
                    echo "Choice: ${params.CHOICE}"

                    script {  datas = readYaml file: './pipeline-config.yml'}
                    echo datas.fruits [0]
                }

            }
            catch (exc) {
                echo 'Something failed, I should sound the klaxons!'
            }
        }

        stage('Build') { 
            steps {
              echo 'build stage step1'
              echo 'build stage step2'
            }
        }
        stage('Test') { 
            steps {
              echo 'Test Stage step 1'
              echo datas.fruits [0]
            }
        }
        stage('Deploy') {
            steps {
              echo 'Deploy Stage step 1'
            }
        }
    }
}
