pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/harmain27-04/MyMavenSeleniumFirefoxApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x gradlew'
                sh './gradlew clean build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Run Firefox Selenium Application') {
            steps {
                sh './gradlew run'
            }
        }
    }

    post {
        success {
            echo 'Firefox Selenium Build Successful!'
        }

        failure {
            echo 'Firefox Selenium Build Failed!'
        }
    }
}
