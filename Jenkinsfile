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
                        fetchUrl: 'https://dl-cdn.alpinelinux.org/alpine/v3.14/releases/x86_64/alpine-minirootfs-3.14.2-x86_64.tar.gz'
                    )
                }
            }
        }
    }
}
