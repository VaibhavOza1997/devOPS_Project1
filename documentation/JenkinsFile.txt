pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/VaibhavOza1997/devOPS_Project1.git',
                        credentialsId: 'github-pat'
                    ]]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t abc-retail-app .'
            }
        }

        stage('Run with Ansible') {
            steps {
                sh 'ansible-playbook ansible/run_docker.yml'
            }
        }
    }
}
