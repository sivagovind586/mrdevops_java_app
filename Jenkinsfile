@Library('my-shared-library') _
pipeline {
    agent any 
    stages {
        stage ("checkout"){
            steps{
                gitCheckout{
                    branch: "main"
                    url: "https://github.com/sivagovind586/mrdevops_java_app.git"
                }
            }
        }
    }
}