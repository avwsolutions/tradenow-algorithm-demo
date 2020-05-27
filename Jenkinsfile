pipeline { 
    agent { label 'docker-slave' }  
    stages { 
        stage('Build') { 
            steps { 
                mvn -h
                echo 'This is a mini pipeline.' 
            }
        }
    }
}
