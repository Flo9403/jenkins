pipeline {

    agent any // Exécute sur n'importe quel agent disponible

    tools {
        jdk 'Java21' // Nom configuré pour votre JDK dans Jenkins
        maven 'Maven3' // Nom configuré pour Maven dans Jenkins
    }

    stages {

        stage('Build') { // Étape de compilation
            steps {
                bat 'mvn clean install' // Utilise une commande compatible Windows
            }
        }

        stage('Test') { // Étape de tests
            steps {
                bat 'mvn test' // Utilise une commande compatible Windows pour exécuter les tests unitaires
            }
        }

        stage('Run') { // Étape d'exécution
            steps {
                bat 'mvn exec:java' // Utilise une commande compatible Windows pour lancer l'application
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
