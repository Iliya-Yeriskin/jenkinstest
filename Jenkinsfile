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
         stage("amd64 - Build and Test") {
            steps {
                script {
                    sh 'echo "this is a test"'
                    extractTestImage: true
                }
                when { not { extractTestImage 'false' } }
                    steps {
                            junit '/usr/src/app/test/build/test-reports/test.xml'
                    }                
                }
            }    
         }
    }
//     post {
//         always {
//             junit allowEmptyResults: true, testResults: '/var/jenkins_home/workspace/test1_main/build/test-reports/test.xml'
//         }    
//     }
}
