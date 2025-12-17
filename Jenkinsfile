pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh '''
                echo "Starting deployment..."

                mkdir -p /var/www/app7

                # Clean old files (important)
                rm -rf /var/www/app7/*

                # Copy everything from repo to web directory
                cp -r ./* /var/www/app7/

                # Remove Jenkinsfile from web root (optional but clean)
                rm -f /var/www/app7/Jenkinsfile

                echo "Deployment completed successfully"
                '''
            }
        }
    }

    post {
        success {
            emailext(
                subject: "✅ SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Build SUCCESS 🎉

Job: ${env.JOB_NAME}
Build: ${env.BUILD_NUMBER}
URL: ${env.BUILD_URL}
""",
                to: "adityasharma965064@gmail.com"
            )
        }

        failure {
            emailext(
                subject: "❌ FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Build FAILED ❌

Job: ${env.JOB_NAME}
Build: ${env.BUILD_NUMBER}
URL: ${env.BUILD_URL}
""",
                to: "adityasharma965064@gmail.com"
            )
        }
    }
}
