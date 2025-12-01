pipeline {
    agent any

    stages {
        stage('Debug System') {
            steps {
                bat '''
                    echo ========== DEBUG INFO ==========
                    echo Дата: %date% %time%
                    echo.
                    echo 1. Поиск Java:
                    where java
                    echo.
                    echo 2. Папки Java в Program Files:
                    dir "C:\\Program Files\\Java"
                    echo.
                    echo 3. Переменная JAVA_HOME:
                    echo JAVA_HOME = %JAVA_HOME%
                    echo.
                    echo 4. PATH переменная:
                    echo %PATH%
                    echo.
                    echo 5. Содержимое диска C: (Java папки):
                    dir "C:\\" | findstr /i "java jdk"
                    echo =================================
                '''
            }
        }

        stage('Test Simple Java') {
            steps {
                bat '''
                    echo Тест простой Java команды:
                    java -version 2>&1
                    if %errorlevel% neq 0 (
                        echo Java НЕ работает из Jenkins!
                    ) else (
                        echo Java работает!
                    )
                '''
            }
        }
    }
}