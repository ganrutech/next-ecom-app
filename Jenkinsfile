pipeline {
    agent any
    tools {nodejs "Node14"}
     environment {
        CI = 'true'
    }
    stages {
        stage("Build") {
            steps {
                echo "Started installing package..."
                sh "npm install"
                sh "npm install -g pm2"
                sh 'npm run build'
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