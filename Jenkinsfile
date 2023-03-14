pipeline {
    agent any
    tools { 
      maven 'MAVEN' 
    }
    stages {
        stage('Build') {
            steps {
                git url: 'https://github.com/Ajinkya-Dhote/MicroServices.git', branch: 'master'
                sh 'mvn -B -DskipTests clean package'
            }
        }
      
    }
}
