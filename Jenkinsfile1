pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat "echo building or so..."
            }
        }
        stage('Run Static Analysis') {
            parallel {
                stage('Model Metrics Analysis') {
                    agent any
                    steps {
                        bat "echo checking model Merics and compare to thresholds"
                    }
                    //post {
                        //always {
                            //junit "**/TEST-*.xml"
                       // }
                    //}
                }
                stage('Modeling Guidelines Checks') {
                    agent any
                    steps {
                        bat "echo Check modeling guidelines"
                    }
                    //post {
                     //   always {
                            //junit "**/TEST-*.xml"
                      //  }
                   // }
                }
            }
        }
        stage('MIL and Codegen') {
            parallel {
                stage('MIL Tests') {
                    agent any
                    steps {
                        bat "echo running MIL Tests"
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
            }
            //post {
            //    always {
                    //junit "**/TEST-*.xml"
            //    }
            //}
        }
        stage('SIL Tests') {
            steps {
                bat "echo running SIL Tests"
            }
            //post {
            //    always {
                    //junit "**/TEST-*.xml"
            //    }
            //}
        }
        stage('finalise') {
            steps {
                bat "echo finalise"
            }
            post {
                always {
                    bat "echo publish report"
                //junit "**/TEST-*.xml"
                }
            }
        }
    }
}
