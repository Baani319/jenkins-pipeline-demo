pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example: Use a build tool like Maven
                // sh 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                // Example: Use testing tools like JUnit
                // sh 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality...'
                // Example: Use SonarQube for code analysis
                // sh 'sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example: Use OWASP Dependency Check
                // sh 'dependency-check --scan ./'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Example: Deploy to AWS EC2
                // sh 'scp target/app.war user@staging-server:/path'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Example: Run post-deployment tests
                // sh 'curl -X GET http://staging-server/health'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
                // Example: Deploy to production server
                // sh 'scp target/app.war user@production-server:/path'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
        success {
            echo 'Pipeline succeeded.'
            mail to: 'baani1903@gmail.com',
                 subject: "SUCCESS: Job '${env.JOB_NAME}' (${env.BUILD_NUMBER})",
                 body: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) completed successfully."
        }
        failure {
            echo 'Pipeline failed.'
            mail to: 'baani1903@gmail.com',
                 subject: "FAILED: Job '${env.JOB_NAME}' (${env.BUILD_NUMBER})",
                 body: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) failed. Check console output at ${env.BUILD_URL}"
        }
    }
}
