pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                git url: 'https://github.com/Ajinkya-Dhote/MicroServices.git', branch: 'master'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
