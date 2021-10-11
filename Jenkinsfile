pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                sh 'echo "this is a test" >> text.xml'
                sh 'pwd'
                sh 'ls -l build/'
            }
        }
    }
    post {
       always {
           junit '/var/jenkins_home/workspace/test1_main/test.xml'
       }
    }
}
