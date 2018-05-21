pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /Users/wizhu/.m2:/home/wizhu/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'cd my-app;mvn -B -DskipTests clean package'
            }
        }
    }
}
