pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat "echo building or so..."
                bat "sleep 5"
            }
        }
        stage('MIL and Codegen') {
            parallel {
                stage('MIL Tests') {
                    agent any
                    steps {
                        bat "echo running MIL Tests"
                        bat "sleep 5"
                    }
                    //post {
                    //    always {
                            //junit "**/TEST-*.xml"
                    //    }
                    //}
                }
                stage('Cogeden') {
                    agent any
                    steps {
                        bat "echo generating Code"
                        bat "sleep 5"
                    }
                    //post {
                    //    always {
                            //junit "**/TEST-*.xml"
                    //    }
                    //}
                }
            }
        }
        stage('MISRA Check') {
            steps {
                bat "echo running MISRA analysis"
                bat "sleep 5"
            }
        }
    }
}
