@Library('my-shared-library') _
pipeline {
    agent any 
    stages {
        stage ("checkout"){
            steps{
                gitCheckout{
                    branch: "main"
                    url: "https://github.com/sivagovind586/jenkins_shared_lib.git"
                }
            }
        }
    }
}