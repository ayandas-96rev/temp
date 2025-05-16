pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/ayandas-96rev/temp.git'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: "${GIT_REPO}"
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Playwright Tests') {
            steps {
                sh 'npx playwright test'
                archiveArtifacts artifacts: 'test-results/*'
            }
        }
    }
}