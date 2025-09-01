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
        echo 'Building React app...'
        sh 'CI=false npm install'
        sh 'CI=false npm run build'
    }
}

stage('Deploy') {
    steps {
        echo 'Deploying to Apache...'
        sh 'sudo rm -rf /var/www/html/*'
        sh 'sudo cp -r build/* /var/www/html/'
    }
}
}
}
