pipeline {
    agent { label "slaveserver" }

    stages {
        stage('Git clone for project') {
            steps {
                echo 'Cloning the project'
                git branch: 'main', url: 'https://github.com/Pooja-gouda/Helloworld-latest.git'
            }
        }
        stage('Maven build') {
            steps {
                echo 'Build the mavem'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
        }
        stage('Deploy project') {
            steps {
                echo 'Deploy project'
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'jid', path: '', url: 'http://18.61.231.206:8080/')], contextPath: null, war: '**/*.war'
            }
        }
        stage('Deploy for test') {
            steps {
                echo 'Test deploy'
            }
        }
        stage('Producation deploy') {
            steps {
                echo 'Producation deploy'
            }
        }
    }
}
