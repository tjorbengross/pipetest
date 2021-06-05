
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                runMATLABCommand "pi"
            }
        }
        stage('Run Tests') {
            parallel {
                stage('Test1') {
                    agent any
                    steps {
                        runMATLABCommand "2*pi"
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
                        runMATLABCommand "3*pi"
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
