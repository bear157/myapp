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
                
                bat 'gh-pages -d build -r https://davy21:$GITHUB_PASSWORD@github.com/davy21/index.git'
                
                echo 'Deploying stage end...'
            }
        }
        
    }
}
