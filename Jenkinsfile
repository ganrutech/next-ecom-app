pipeline {
    agent any
    tools {nodejs "Node17"}
     environment {
        CI = 'true'
    }
    stages {
        stage("Build") {
            steps {
                echo "Started installing package..."
                sh "npm install"
                sh "chmod +x ${env.WORKSPACE}/jenkins/scripts/build.sh"
                sh './jenkins/scripts/build.sh'
            }
        }
        stage("Test") {
            steps {
                echo "Test script completed.."
            }
        }
        stage("Start") {
            steps {
                sh "chmod +x ${env.WORKSPACE}/jenkins/scripts/server.sh"
                sh './jenkins/scripts/server.sh'
            }
        }
    }
}