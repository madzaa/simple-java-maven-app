pipeline{
    agent {
        kubernetes {
            label 'test-app'
            defaultContainer 'maven'
            idleMinutes 3
            yamlFile 'build-pod.yaml'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {}
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}