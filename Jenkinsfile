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
                sh 'cat text.xml'
                sh 'ls -l'
            }
        }
    }
    post {
       always {
           junit 'test.xml'
       }
    }
}
