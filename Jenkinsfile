pipeline {
    agent { label 'Mikrus-Frog' }

    stages {
        stage('Detekcja Zmian') {
            steps {
                checkout scm
                
                sh '''
                    echo "--- ALERT: Wykryto zmiany w repozytorium! ---"
                    echo "Data wykrycia: $(date)"
                    echo "Ostatni commit: $(git log -1 --pretty=format:'%h - %s')"
                    
                    echo "Jenkins widział zmianę o $(date)" >> /home/frog/powiadomienia_jenkins.log
                '''
            }
        }
    }
    
    post {
        success {
            echo 'Sukces! Jenkins odebrał sygnał i wykonał zadanie.'
        }
    }
}
