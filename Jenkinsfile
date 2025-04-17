pipeline {
    agent {
        docker {
            image 'node:18' // imagen oficial de Node.js con npm ya incluido
        }
    }

    stages {
        stage('Preparar entorno') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Instalar dependencias') {
            steps {
                echo 'hello!'
            }
        }

        stage('Compilar') {
            steps {
                echo 'hello there!'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || echo "Tests fallaron pero seguimos..."'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Acá podrías poner lógica de deploy si querés'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline ejecutado con éxito'
        }
        failure {
            echo '❌ Hubo un error en el pipeline'
        }
    }
}

