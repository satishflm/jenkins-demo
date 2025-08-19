pipeline {
    agent { label 'master' }
    environment {
        BRANCH_NAME = "${env.GIT_BRANCH}"
        COMMIT_SHA = "${env.GIT_COMMIT}"
        PUSHER = "${env.GIT_AUTHOR_EMAIL}"
    }
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        stage('Print Info') {
            steps {
                echo "Build triggered by GitHub push!"
                echo "Branch: ${BRANCH_NAME}"
                echo "Commit SHA: ${COMMIT_SHA}"
                echo "Pusher: ${PUSHER}"
            }
        }
        stage('Run Python Script') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}
