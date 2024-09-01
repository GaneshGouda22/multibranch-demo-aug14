pipeline {
    agent any
    tools {
        maven 'MAVEN_3.9.8'
    }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git',
                    branch: 'main'
            }
        }
        stage('build') {
            steps {
                sh 'building code.....'
                sh 'static code analysis'
                sh 'archive the package into jfrog'
            }
        }
        stage('deploy-prod') {
            steps {
                sh 'deploy into production'
            }
        }
    }
}
