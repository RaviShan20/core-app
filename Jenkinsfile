pipeline {
    agent any
    tools {
        maven "maven-3.6.2"
    }

    stages {
        stage('Build') {
            steps {
                 scm checkout
              //  git branch: 'main', url: 'https://github.com/DevOpsABB22/core-app.git'
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
