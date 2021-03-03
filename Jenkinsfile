pipeline {
    agent any
    
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
