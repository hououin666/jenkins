pipeline {
    agent any

    stages {
        stage('Checkout Git') {
            steps {
                git url: 'https://github.com/hououin666/jenkins.git', branch: 'master'
            }
        }

        stage('Build with Maven') {
            steps {
                bat '''
                    echo ====================================
                    echo Сборка проекта с Maven
                    echo ====================================

                    REM Проверяем Maven
                    "C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn.cmd" --version

                    echo.
                    echo Запускаем сборку проекта...
                    echo.

                    REM Собираем проект
                    "C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn.cmd" clean compile

                    echo.
                    echo Сборка успешно завершена!
                '''
            }
        }

        stage('Package') {
            steps {
                bat '''
                    echo Создаем JAR пакет...
                    "C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn.cmd" package -DskipTests
                '''
            }
        }
    }

    post {
        always {
            echo '===================================='
            echo 'Pipeline завершен'
            echo '===================================='
        }
        success {
            bat 'echo УСПЕХ! Проект успешно собран!'
        }
        failure {
            bat 'echo НЕУДАЧА. Проверьте логи ошибок.'
        }
    }
}