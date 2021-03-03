pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'building stage...'
                
                bat 'npm install'
                bat 'npm install gh-pages --save-dev'
                bat 'npm run build'         

                echo 'building stage end...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying stage...'

                bat 'npm run deploy'

                echo 'Deploying stage end...'
            }
        }
        
    }
}
