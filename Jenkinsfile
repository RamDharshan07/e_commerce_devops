pipeline {
    agent any

    environment {
        // Change this to your actual deploy folder path
        DEPLOY_DIR = "C:/Users/RAM DHARSHAN.E/Desktop/ecommerce-deploy"
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull code from your GitHub repo using Jenkins credentials
                git branch: 'main',
                    url: 'https://github.com/RamDharshan07/e_commerce_devops.git',
                    credentialsId: 'github-pat'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for static site'
            }
        }

        stage('Test') {
            steps {
                echo 'Optional: HTML/CSS/JS validation can go here'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying website to ${DEPLOY_DIR}"
                bat """
                if not exist "${DEPLOY_DIR}" mkdir "${DEPLOY_DIR}"
                xcopy /E /Y * "${DEPLOY_DIR}\\"
                """
            }
        }
    }
}
