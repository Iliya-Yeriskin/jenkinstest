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
                sh 'mkdir build && cd build && mkdir reports'
                                sh 'cd reports && touch text.xml'
            }
                    post {
             always {
                   junit 'test.xml'
                    }
             }
        }
    }
}
