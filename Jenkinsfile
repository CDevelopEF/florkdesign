pipeline {
    agent any  // Ejecutar en cualquier nodo
     environment {
        PATH = "/usr/local/bin:$PATH"
    }
    stages {
        stage('Info') {
            steps {
                sh 'whoami'
                sh 'hostname'
                sh 'which npm || echo "npm no encontrado"'
                sh 'env'
            }
        }
    }
    stages {
        // Etapa de construcción
        stage('Build') {
            steps {
                script {
                    // Instalar dependencias y construir el proyecto
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        // Etapa de pruebas
        stage('Test') {
            steps {
                script {
                    // Ejecutar las pruebas
                    sh 'npm test'
                }
            }
        }

        // Etapa de despliegue
        stage('Deploy') {
            steps {
                script {
                    // Comando para desplegar (esto dependerá de tu flujo de trabajo)
                    sh './deploy.sh'
                }
            }
        }
    }

    post {
        success {
            echo 'El pipeline se ejecutó con éxito'
        }
        failure {
            echo 'Hubo un error en el pipeline'
        }
    }
}
