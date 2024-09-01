pipeline {
    agent any
    tools {
        maven 'MAVEN_3.9.8'
    }
    triggers {
        pollSCM('* * * * *')
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
                sh 'quality gate'
            }
        }
        stage('deploy')
        {
            steps {
                sh 'using terraform create env'
                sh 'use kubectl to deploy'
            }
        }
        stage('test') {
            steps {
                sh 'run end to end system tests'
                sh 'display test results'
            }
        }

    }
}
