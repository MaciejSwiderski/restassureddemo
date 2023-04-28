pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                git 'https://github.com/MaciejSwiderski/restassureddemo.git'
            }
        }

         stage('build test') {
            steps {
                bat 'mvn clean test'
            }
        }

         stage('Publish HTML report') {
            steps {
              publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/surefire-reports', reportFiles: 'emailable-report.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }
}
