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
                sh 'echo building code.....'
                sh 'echo static code analysis'
                sh 'echo archive the package into jfrog'
                sh 'echo quality gate'
            }
        }
        stage('deploy')
        {
            steps {
                sh 'echo using terraform create env'
                sh 'echo use kubectl to deploy'
            }
        }
        stage('test') {
            steps {
                sh 'echo run end to end performance tests'
                sh 'echo display test results'
            }
        }

    }
}
