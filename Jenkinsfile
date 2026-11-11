pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'Java'
    }
    stages {
        stage('Checkout') {
            steps {
                echo '📥 Obteniendo código fuente...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo '🔨 Compilando proyecto...'
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                echo '🧪 Ejecutando pruebas unitarias...'
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo '📦 Generando archivo JAR...'
                sh 'mvn package -DskipTests'
            }
        }
    }
}
