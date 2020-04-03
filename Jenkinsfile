node("OpenBook") {

    stage('Download') {
             downloadRepo {
                 name = 'zendesk-java-client'
                 branch = 'master'
             }
    }

    stage('Build') {
             mvn {
                 command = 'clean install -DskipTests -U'
             }
    }

    stage('Test') {
                mvn {
                    command = 'org.jacoco:jacoco-maven-plugin:prepare-agent surefire:test'
                }
    }

    stage('artifactory') {
       artifactory {}
    }
}