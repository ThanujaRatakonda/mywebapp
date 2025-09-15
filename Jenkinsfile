pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Run Ansible playbook to deploy WAR to Tomcat
                bat 'ansible-playbook C:\\path\\to\\deploy-tomcat.yml -i C:\\path\\to\\inventory.ini'
            }
        }
    }

    post {
        success {
            echo 'Build, tests, and deploy completed successfully!'
        }
        failure {
            echo 'Build, tests, or deploy failed.'
        }
    }
}

