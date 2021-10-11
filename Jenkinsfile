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
                sh 'echo "this is a test" >> build/test-reports/text.xml'
                sh 'pwd'
                sh 'ls -l build/test-reports/'
            }
        }
    }
    post {
        always {
           junit '/var/jenkins_home/workspace/test1_main/build/test-reports/test.xml'
        }    
    }
}
