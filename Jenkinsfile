pipeline {
    agent any

    stages {
        stage('Checkout Git') {
            steps {
                git url: 'https://github.com/hououin666/jenkins.git', branch: 'master'
            }
        }

        stage('Build with Absolute Path') {
            steps {
                bat '''
                    echo ====================================
                    echo Сборка с абсолютным путем к Maven
                    echo ====================================

                    "C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn.cmd" --version
                    echo.
                    "C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn.cmd" clean install -DskipTests
                '''
            }
        }
    }

    post {
        always {
            echo 'Сборка завершена'
        }
    }
}