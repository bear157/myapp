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

                dir('build') {
                    
                    withCredentials([usernamePassword(credentialsId: 'bear157', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){
                        echo USERNAME
                        echo PASSWORD
                    
                        bat 'git init'
                        bat 'git remote add build https://github.com/bear157/myapp.git'
                    
                        bat 'git add .'
                        bat 'git commit -m "build"'
                        bat 'git branch gh-pages'
                        bat 'git checkout gh-pages'
                        bat 'git push build gh-pages'
                    }
                }
                

                echo 'Deploying stage end...'
            }
        }
        
    }
}
