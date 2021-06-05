
pipeline {
    agent none
    stages {
        stage('Run Tests') {
            parallel {
                stage('Test1') {
                    agent any
                    steps {
                        bat "echo test1"
                    }
                    post {
                        always {
                            junit "**/TEST-*.xml"
                        }
                    }
                }
                stage('Test2') {
                    agent any
                    steps {
                        bat "echo test2"
                    }
                    post {
                        always {
                            junit "**/TEST-*.xml"
                        }
                    }
                }
            }
        }
    }
}
