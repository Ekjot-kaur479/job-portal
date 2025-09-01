pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:Ekjot-kaur479/job-portal.git',
                    credentialsId: 'jenkins-github-key'
            }
        }
        stage('Build') {
            steps {
                echo 'Building project...'
                sh 'ls -l'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to EC2...'
               
                sh 'sudo cp -r * /var/www/html/'
            }
        }
    }
}
