@Library('piper-lib-os') _

pipeline {
    agent any

    stages {
        stage('Protecode Security Scan') {
            steps {
                script {
                    protecodeExecuteScan(script: this)
                }
            }
        }
    }
}
