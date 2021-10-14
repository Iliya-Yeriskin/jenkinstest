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
                sh 'pwd'
            }
        }
    }
    post {
        always {
            junit allowEmptyResults: true, testResults: '/var/jenkins_home/workspace/test1_main/build/test-reports/test.xml'
        }    
    }
}
