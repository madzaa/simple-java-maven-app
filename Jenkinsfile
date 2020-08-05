pipeline{
    agent {
        kubernetes {
            label 'test-app'
            defaultContainer 'maven'
            idleMinutes 3

        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}