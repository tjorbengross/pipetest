
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat "echo build"
            }
        }
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
