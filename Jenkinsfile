pipeline {
    agent any

    stages {
        stage('Copier index.html') {
            steps {
                bat '''
                    copy index.html C:\\www\\html\\index.html /Y
                '''
            }
        }

        stage('Redémarrer le service web') {
            steps {
                bat '''
                    net stop W3SVC
                    net start W3SVC
                '''
            }
        }
    }

    post {
        success {
            echo 'Déploiement HTML effectué et le service web a été redémarré.'
        }
        failure {
            echo 'Une erreur est survenue pendant le déploiement.'
        }
    }
}
