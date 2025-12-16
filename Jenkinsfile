pipeline {
    agent any

    stages {
        stage('Get Code') {
            steps {
                git 'https://github.com/Tech-Contributors/app7.techcontributors.git'
            }
        }

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
