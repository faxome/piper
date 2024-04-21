@Library('piper-lib-os') _

pipeline {
    agent any

    stages {
        stage('Protecode Security Scan') {
            steps {
                script {
                    protecodeExecuteScan(
                        script: this, 
                        protecode: [ 
                            serverUrl: 'https://qa.bdba.tools.sap',
                            group: '1640',
                            userTokenCredentialsId: 'AAAVw02ZjkVPRo0Dzs10fTadAXi2jZ9Nb8ZmY7yVPImCZ0PY'
                        ],
                    )
                }
            }
        }
    }
}
