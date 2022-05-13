pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    //     stage('Sonar-Report') {
    //         steps {
    //         sh 'mvn clean install sonar:sonar -Dsonar.host.url=http://44.202.186.72:9000 -Dsonar.analysis.mode=publish -Dsonar.login=admin -Dsonar.password=Ujjwal@123'
    //     }
    // }
}
}