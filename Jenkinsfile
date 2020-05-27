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
    }
}
