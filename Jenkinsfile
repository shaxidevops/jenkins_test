pipeline {
    agent any
    environment {
        name= 'Nawaz Sharif'
    }
    parameters{
        string(name: 'Person', defaultValue: 'Ali Ahmad', description: "This is the dafult name and values for this pipeline")
        booleanParam(name: 'isMale', defaultValue: true , description: "")
    }
    stages {
        stage('Shell Commands') {
            steps {
                sh 'date'
                sh 'pwd'
            }
        }
        stage('Environment Variables') {
            environment{
                user= 'Nawaz Sharif'
            }
            steps {
                echo "${BUILD_ID}"
                echo "${user}"
            }
        }
        stage('Deploy Parameters') {
            steps {
                sh 'echo "${name}"'
                sh 'echo ${description}'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
            }
            steps {
                echo "deploy on prod"
            }
        }
        stage('Deploy on Build') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
