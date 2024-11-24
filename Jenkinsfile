pipeline {

    agent any // Exécute sur n'importe quel agent disponible

    tools {
        jdk 'JDK17' // Nom configuré pour votre JDK dans Jenkins
        maven 'Maven3' // Nom configuré pour Maven dans Jenkins
    }

    stages {

        stage('Build') { // Étape de compilation
            steps {
                sh 'mvn clean install' // Exécute la commande Maven pour compiler le projet
            }
        }

        stage('Test') { // Étape de tests
            steps {
                sh 'mvn test' // Exécute les tests unitaires
            }
        }

        stage('Run') { // Étape d'exécution
            steps {
                sh 'mvn exec:java' // Lance l'application (optionnel)
            }
        }

    }

    post { // Actions après l'exécution de la pipeline
        success {
            echo 'Pipeline exécuté avec succès!'
        }
        failure {
            echo 'Pipeline échoué!'
        }
    }
}
