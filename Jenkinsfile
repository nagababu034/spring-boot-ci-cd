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
                sh './gradlew clean build'
            }
        }
//          stage('Test') {
//             steps {
//                 sh './gradlew test'
//             }
//         }
//         stage('Build Jar') {
//             steps {
//                 sh 'gradle bootJar'
//             }
//         }

    }
}