@Library('piper-lib-os') _

pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                script {
                    // Загрузка файла в рабочую директорию, если еще не загружен
                    sh "curl -o alpine-minirootfs.tar.gz https://dl-cdn.alpinelinux.org/alpine/v3.14/releases/x86_64/alpine-minirootfs-3.14.2-x86_64.tar.gz"
                }
            }
        }
        stage('Protecode Security Scan') {
            steps {
                script {
                    echo "Using server URL: ${protecode.serverUrl}"
                    protecodeExecuteScan(
                        script: this, 
                        protecode: [ 
                            serverUrl: 'https://qa.bdba.tools.sap',
                            group: '1640',
                            userTokenCredentialsId: 'AAAVw02ZjkVPRo0Dzs10fTadAXi2jZ9Nb8ZmY7yVPImCZ0PY' // ID учетных данных из Jenkins
                        ],
                        filePath: 'alpine-minirootfs.tar.gz' // Локальный путь к файлу
                    )
                }
            }
        }
    }
}
