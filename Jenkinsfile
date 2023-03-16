@Library('shared-lib') _
// welcome 'Test User'
pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew clean'
            }
        }
         stage('Test') {
            steps {
                sh 'gradle test'
            }
        }
//         stage('Build Jar') {
//             steps {
//                 sh 'gradle bootJar'
//             }
//         }

    }
}