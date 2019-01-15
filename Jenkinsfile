#!groovy

pipeline {
    agent any /*{
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }*/
    stages {

        stage('Initialization') {
            steps {
                script {  datas = readYaml file: './pipeline-config.yml'}
                echo datas.fruits [0]
            }
        }
        stage('Build') { 
            steps {
                //sh 'npm install' 
              echo 'build stage step1'
              
              // do something
              
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
