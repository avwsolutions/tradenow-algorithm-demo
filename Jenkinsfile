pipeline { 
    agent { label 'docker-slave' }
    tools {
        maven 'tradenow-demo'
        jdk 'tradenow-demo'
     }
    stages { 
        stage('Build') { 
            steps {
                echo 'Start Maven Package process and run an Unit test'
                sh 'mvn package'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
        stage('JAR Sign') {
            steps {
                venafiCodeSignWithJarSigner certLabel: 'Test-Jarsigner-FullStaq', extraArgs: '', file: 'target/algorithm-secret-1.0-SNAPSHOT.jar', timestampingServers: '', tppName: 'Venafi Demo Environment'
            }       
        }
        stage('JAR Validate') {
            steps {
                venafiVerifyWithJarSigner certLabel: 'Test-Jarsigner-FullStaq', glob: 'target/*.jar', tppName: 'Venafi Demo Environment'
            }       
        }
        stage('Reveal Secret') {
            steps {
                sh 'java -jar target/algorithm-secret-1.0-SNAPSHOT.jar'
            }       
        }

    }
}
