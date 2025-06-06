pipeline {
    agent {
        label 'agent-lftp'
    }
    stages {
        stage('Clone repo') {
            steps {
                git branch: 'main', url: 'https://github.com/st-ac/TP_Landingpage_deployment_cda'
            }
        }
        stage('LFTP') {
            steps {
                sh 'lftp -u "$login","$mdp" -e "set ftp:ssl-force true; set ftp:ssl-protect-data true; mirror -R /home/jenkins/workspace/Steph_TP_HTML/ www/; bye" ftps://"$ftp" '
            }
        }
    }
}
