pipeline {
    agent none
    environment {
        TEXT = 'example'
    }

    stages {
        stage('Parallel Stages') {
            parallel {
                stage('Uppercase on Development') {
                    agent {
                        label 'development'
                    }
                    steps {
                            sh 'gcc -o uppercase uppercase.c'
                            sh "./uppercase ${TEXT}"
                            sh "uname -a"
                        }
                }

                stage('Reverse on Development2') {
                    agent {
                        label 'development2'
                    }
                    steps {
                            sh 'gcc -o reverse reverse.c'
                            sh "./reverse ${TEXT}"
                            sh "uname -a"
                        }
                }
            }
        }
    }
}
