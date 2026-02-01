pipeline {
    agent { label "agentserver" }

    stages {
        stage('Clone') {
            steps {
                echo 'Clone project'
                git branch: 'main', url: 'https://github.com/Pooja-gouda/Helloworld-latest.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Build project'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploy project'
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'jenkinsid', path: '', url: 'http://40.192.36.41:8080/')], contextPath: null, war: ' **/*.war'
            }
        }
        stage('deploy for test') {
            steps {
                echo 'Deploy project testing'
            }
        }
        stage('deploy production') {
            steps {
                echo 'Deploy project for production'
            }
        }
    }
}
