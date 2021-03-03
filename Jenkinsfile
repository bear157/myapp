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

                bat 'git push origin :gh-pages'
                bat 'cd build'
                bat 'git init'
                bat 'git remote add build https://github.com/bear157/myapp.git'
                bat 'git branch gh-pages'
                bat 'git add .'
                bat 'git commit -m "build"'
                bat 'git checkout gh-pages'
                bat 'git push build gh-pages'

                echo 'Deploying stage end...'
            }
        }
        
    }
}
