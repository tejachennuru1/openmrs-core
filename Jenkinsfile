pipeline {
    agent { label 'jdk8' }
    parameters { string(name: 'build', defaultValue: 'package', description: 'teja') }

    triggers { cron('*/5 * * * *') }
    stages {
        stage('git') {
            steps {
                git branch: 'teja', url: 'https://github.com/tejachennuru1/openmrs-core.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn  ${params.build}'
            }
        }
        stage('artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*.jar'
            }
        }
        stage('archive results') {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}
