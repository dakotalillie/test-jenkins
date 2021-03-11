pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo "Installing"
            }
        }
        stage('Test (Static)') {
            parallel {
                stage('Validate') {
                    steps {
                        echo "Validating"
                    }
                }
                stage('Format') {
                    steps {
                        echo "Formatting"
                    }
                }
                stage('Lint') {
                    steps {
                        echo "Linting"
                    }
                }
            }
        }
        stage('Test (Unit)') {
            steps {
                echo "Unit testing"
            }
        }
        stage('Publish') {
            when {
                buildingTag()
            }
            parallel {
                stage('Artifactory (Release)') {
                    steps {
                        echo "Publishing release"
                    }
                }
                stage('Artifactory (Latest)') {
                    steps {
                        echo "Publishing latest"
                    }
                }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}
