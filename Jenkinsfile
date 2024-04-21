@Library('piper-lib-os') _

pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                script {
                    // Загрузка файла в рабочую директорию (пример использует sh, также можно использовать bat для Windows)
                    sh "curl -o alpine-minirootfs.tar.gz https://dl-cdn.alpinelinux.org/alpine/v3.14/releases/x86_64/alpine-minirootfs-3.14.2-x86_64.tar.gz"
                }
            }
        }
        stage('Protecode Security Scan') {
            steps {
                script {
                    protecodeExecuteScan(
                        script: this, 
                        protecode: [ 
                            serverUrl: 'https://qa.bdba.tools.sap',
                            group: '1640',
                            userTokenCredentialsId: 'AAAVw02ZjkVPRo0Dzs10fTadAXi2jZ9Nb8ZmY7yVPImCZ0PY' // Заменено на ID учетных данных из Jenkins
                        ],
                        filePath: 'alpine-minirootfs.tar.gz' // Используем локальный файл вместо URL
                    )
                }
            }
        }
    }
}
