pipeline { 
    agent { label 'docker-slave' }  
    stages { 
        stage('Build') { 
            steps { 
                sh 'mvn -h'
                echo 'This is a mini pipeline.' 
            }
        }
    }
}
