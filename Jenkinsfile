pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh '''
                mkdir -p /var/www/app7
                cp -r * /var/www/app7/
                '''
            }
        }
    }
}
