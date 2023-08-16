pipeline {
    agent any 
    stages {
        stage ("checkout"){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/sivagovind586/mrdevops_java_app.git'
                }
            }
        }
    }
}