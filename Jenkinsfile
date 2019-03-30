pipeline {
    agent {
        node {
            label 'master'
            customWorkspace '/var/jenkins_home/workspace/Java-Web-Project'
         }
    }
    stages {
        stage('Build') {
            steps {
                sh 'pwd'
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