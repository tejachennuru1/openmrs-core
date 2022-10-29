pipeline {
    agent  any

    stages {
        stage('git')
            steps {
                git branch: 'master', url: 'https://github.com/tejachennuru1/openmrs-core.git'
            }
    }
    stage('build')
        steps {
            sh 'mvn package'
        }
    stage('artifacts')
        steps {
            archiveArtifacts artifacts: '**/*.jar'
        }

    stage('archive results')
        steps {
            junit '**/surefire-reports/*.xml'
        }
}
