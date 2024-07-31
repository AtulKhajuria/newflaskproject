pipeline {
agent any

stages {
        stage('Build') {
            steps {
            // Get some code from a GitHub repository
            git url: 'https://github.com/AtulKhajuria/newflaskproject.git'

            // Run Maven on a Unix agent.
            script{
            if(isUnix()){
            sh "pip install -r requirements.txt"
            }
            else{
            bat ""
            }
            }
}
}



stage('Unit Test') {
    steps {

    // Run Maven on a Unix agent.
    script{
        if(isUnix()){
        sh "pytest"
        }
        else{
        bat "pytest"
        }
        }
        }

    }

    stage('Docker Build') {
            steps {
                script{
                if(isUnix()){
                sh "docker build -t  atulkhajuria/newflaskapp."
                }
                else{
                 bat "docker build -t atulkhajuria/newflaskapp."
                 }
                 }
            }
        }
}
}