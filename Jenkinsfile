pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                sh 'printenv'
            }
        }
        stage('is-pr') {
            when {
                branch 'PR-*'
            }
            steps {
                echo "I'm a PR!"
            }
        }
    }
}
