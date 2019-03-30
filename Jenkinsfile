pipeline {
    agent none
    stages {
        stage('Build') {
            steps {
                sh 'build.sh'
            }
        }
        stage('Test') {
            steps {
                sh 'test.sh'
            }
        }
        stage('Deploy to Production Environment') {
            steps {
                sh 'docker build -t mengqingyang/tomcat .'
                sh 'docker run mengqingyang/tomcat -p 80:8080'
            }
        }
    }
}