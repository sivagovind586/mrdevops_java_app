@Library('my-shared-library') _
pipeline {
    agent any
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')


    } 
    stages {
        
        stage ("checkout"){
        when{expression { params.action == 'create'} }

            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/sivagovind586/mrdevops_java_app.git"
            )
            }
        }
        stage ("unit test maven"){
        when{expression { params.action == 'create'} }
            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage ("Integration for maven"){
        when{expression { params.action == 'create'} }
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
        stage ("static code analysis"){
        when{expression { params.action == 'create'} }
            steps{
                script{
                    def SonarQubecredentialsId = 'sonar-api'
                    staticCodeAnalysis(SonarQubecredentialsId)
                }
            }
        }

    }
}