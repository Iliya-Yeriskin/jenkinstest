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
            environment {
                arch = "amd64"
            }
            steps {
                script {
                    configFileProvider([configFile(fileId: 'github-npm-manna-delivery', targetLocation: '.npmrc')]) {
                        sh "chmod o+r .npmrc"
                        def containerImage = dockerBuild (
                            containerImageName: env.image_name,
                            containerImageTag: "${version}-${arch}",
                            containerBuildArgs: ["OS_VERSION=${nodeVersion}-${env.nodeImageOS}"],
                            registryAddress: "${env.aws_account}.dkr.ecr.${env.aws_region}.amazonaws.com",
                            pushImage: true
                            extractTestImage: true
                        )
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
