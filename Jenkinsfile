pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Этот stage уже есть автоматически
                echo 'Checkout выполнен'
            }
        }

        stage('Build') {
            steps {
                // Используйте ПОЛНЫЙ путь к Maven
                bat 'C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn --version'
                bat 'C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn clean compile -DskipTests'
            }
        }

        stage('Package') {
            steps {
                bat 'C:\\Users\\redlikeroses\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn package -DskipTests'
            }
        }
    }

    post {
        always {
            echo 'Сборка завершена'
        }
        success {
            echo 'УСПЕХ!'
        }
        failure {
            echo 'ПРОВАЛ :('
        }
    }
}