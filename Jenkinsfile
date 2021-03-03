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

                bat 'git branch -r'
                bat 'git branch -l'

                bat 'git config --global user.email "jxyee981101@gmail.com"'
                bat 'git config --global user.name "bear157"'
                bat 'git remote set-url origin "https://secret.ACTIONS_DEPLOY_ACCESS_TOKEN@github.com/bear157/myapp"'

                bat 'npm run deploy'

                echo 'Deploying stage end...'
            }
        }
        
    }
}
