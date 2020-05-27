pipeline { 
    agent { label 'docker-slave' }
    tools { maven 'tradenow-demo' }
    stages { 
        stage('Build') { 
            steps { 
                sh 'mvn -h'
                echo 'This is a mini pipeline.' 
            }
        }
    }
}
