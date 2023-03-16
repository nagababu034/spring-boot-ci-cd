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

        stage("S3 Upload"){
            steps{
                withAWS(region:"us-east-1", credentials:"AWS_CREDENTIAL_ID"){
                    s3Upload(file:"build/libs/*-SNAPSHOT.jar", bucket:"ec2-deploy-bucket")
                }
            }
        }
    }
}