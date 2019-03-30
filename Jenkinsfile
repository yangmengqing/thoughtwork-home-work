pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'cd /var/jenkins_home/workspace/Java-Web-Project && ./build.sh'
            }
        }
        stage('Test') {
            steps {
                sh 'cd /var/jenkins_home/workspace/Java-Web-Project && ./test.sh'
            }
        }
        stage('Deploy to Production Environment') {
            steps {
                sh 'cd /var/jenkins_home/workspace/Java-Web-Project && docker build -t mengqingyang/tomcat .'
                sh 'docker run mengqingyang/tomcat -p 80:8080 -v /var/run/docker.sock:/var/run/docker.sock'
            }
        }
    }
}