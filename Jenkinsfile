pipeline {
    agent any
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'false'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/mau-mv/nginx-ansible-playbook.git', branch: 'main'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook playbook: 'site.yml', inventory: 'hosts'
            }
        }
    }
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
