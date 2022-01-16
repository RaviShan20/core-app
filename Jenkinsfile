pipeline {
    agent any

    tools {
        maven "maven-3.8.4"
    }

    stages {
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/RaviShan20/core-app.git'

                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {
                
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
