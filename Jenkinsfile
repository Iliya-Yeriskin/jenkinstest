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
            }
        }
    }
    post {
       always {
           junit 'tests/results/test.xml'
       }
    }
}
