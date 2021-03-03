pipeline {
    agent any
    
    //Setting the environment variables DISABLE_AUTH and DB_ENGINE
    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'mysql'
    }

    stages {

        stage('Build') {
            steps {
                echo 'building stage...'
                
                bat 'npm install'
                
                bat 'npm run build'         

                echo 'building stage end...'
            }
        }


        stage('Deploy') {
            steps {
                echo 'Deploying stage...'
                
                bat 'npm run test-deploy-jx'
                
                echo 'Deploying stage end...'
            }
        }
        
    }
}
