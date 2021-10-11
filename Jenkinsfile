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
                sh 'cd build/reports && echo "this is a test" >> text.xml'
            }
                    post {
             always {
                   junit 'test.xml'
                    }
             }
        }
    }
}
