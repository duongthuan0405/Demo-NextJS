pipeline {
    agent any

    stages {

        stage('Preview') {
            steps {
               sh 'echo Preview 1'
               sh 'echo Preview 2'
            }
        }

        stage('Checkout') {
            when {
                anyOf {
                    branch 'main'
                    changeRequest target: 'main'
                }
            }

            steps {
               sh 'echo Checkout 1'
               sh 'echo Checkout 2'
            }
        }

        stage('Restore') {
            when {
                anyOf {
                    branch 'main'
                    changeRequest target: 'main'
                }
            }

            steps {
               sh 'echo Restore 1'
               sh 'echo Restore 2'
            }
        }

        stage('Build') {
            when {
                anyOf {
                    branch 'main'
                    changeRequest target: 'main'
                }
            }

            steps {
               sh 'echo Build 1'
               sh 'echo Build 2'
            }
        }

        stage('Test') {
            when {
                anyOf {
                    branch 'main'
                    changeRequest target: 'main'
                }
            }

            steps {
                sh 'echo Build 1'
                sh 'echo Build 2'
            }
        }

        stage('Deploy') {
            when {
                branch 'main' // Chỉ deploy khi merge vào branch main
            }
            steps {
                echo 'Deploying to Server...'
            }
        }
    }

    post {
        always {
            echo 'Kết thúc pipeline!'
        }
        success {
            echo 'Build thành công rực rỡ!'
        }
        failure {
            echo 'Build thất bại, kiểm tra lại code đi Thuận ơi!'
        }
    }
}