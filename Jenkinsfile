pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Obteniendo código fuente desde repositorio...'
                // Si se ejecuta en un servidor Jenkins independiente:
                // git 'https://github.com/Anto-Jaimes/GOLAZO.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Compilando y preparando dependencias...'
                sh 'npm install || true'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Ejecutando suite de pruebas unitarias...'
                sh 'npm test'
            }
        }
    }
    post {
        always {
            echo 'Pipeline finalizado.'
        }
        success {
            echo '¡Construcción y pruebas exitosas en Jenkins!'
        }
        failure {
            echo 'Hubo un error en la ejecución del Pipeline.'
        }
    }
}
