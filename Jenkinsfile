pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                sh 'printenv'
            }
        }
        stage('is-main') {
            when {
                branch 'main'
            }
            steps {
                echo "I'm main!"
            }
        }
        stage('is-pr') {
            when {
                changeRequest()
            }
            steps {
                echo "I'm a PR!"
            }
        }
        stage('is-tag') {
            when {
                buildingTag()
            }
            steps {
                echo "I'm a tag!"
            }
        }
    }
}
