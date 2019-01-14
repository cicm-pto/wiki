#!groovy
import static org.junit.Assert

pipeline {
    agent any /*{
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }*/
    stages {

        stage('Initialization') {
            def datas = readYaml file: 'pipeline-config.yml', text: "something: 'Override'"
            echo assert datas.something == 'Override'
            echo datas.el
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
            }
        }
        stage('Deploy') {
            steps {
              echo 'Deploy Stage step 1'
            }
        }
    }
}
