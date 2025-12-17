pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh '''
                mkdir -p /var/www/app7
                cp -r index.html /var/www/app7/
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
            to: "adityasharma965064@gmail.com",
            recipientProviders: []
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
            to: "adityasharma965064@gmail.com",
            recipientProviders: []
        )
    }
}
}
