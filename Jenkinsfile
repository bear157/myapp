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

                bat 'gh-pages -d build -r https://554be9a0cc41eacab546917b3f3606b407d5bd93@github.com/bear157/myapp.git'


                echo 'Deploying stage end...'
            }
        }
        
    }
}
