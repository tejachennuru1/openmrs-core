node('jdk8') {
    stage('VCS') {
        git branch:'satish', url: 'https://github.com/tejachennuru1/openmrs-core.git'
    stage("build") {
        // sh '/usr/bin/mvn /usr/share/man/man1/mvn.1.gz'
        sh 'mvn clean package'
    }  
    stage("archive results") {
        junit '**/surefire-reports/*.xml'
    }      
}    