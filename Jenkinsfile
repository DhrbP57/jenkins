pipeline {
    agent any

    stages {
        stage('Detekcja Zmian') {
            steps {
                checkout scm
                
                sh '''
                    echo "--- ALERT: Wykryto zmiany w repozytorium! ---"
                    echo "Akcja wykonana na głównym agencie Jenkinsa."
                    echo "Data: $(date)"
                    echo "Ostatni commit: $(git log -1 --pretty=format:'%h - %s')"
                '''
            }
        }
    }
    
    post {
        success {
            echo 'Sukces! Główny agent odebrał sygnał i wykonał zadanie.'
        }
    }
}
