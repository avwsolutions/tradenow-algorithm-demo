pipeline { 
    agent { label 'docker-slave' }
    tools {
        maven 'tradenow-demo'
        jdk 'tradenow-demo'
     }
    stages { 
        stage('Build') { 
            steps { 
                sh 'mvn package'
                echo 'This is a mini pipeline.' 
            }
        }
    }
}
