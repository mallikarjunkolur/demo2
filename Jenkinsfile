pipeline {
    agent any
    stages {
        stage('clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        success {
            echo "build success"
            mail to: "build.mallikarjun.k@gmail.com",
            subject: "notify about build",
            body: "build is success you can check artifact"    
        }
        failure {
            echo "build failed"
        }
    }
}
