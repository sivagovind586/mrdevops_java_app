@Library('my-shared-library') _
pipeline {
    agent any
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')


    } 
    stages {
        when{expression { param.action == 'create'} }
        stage ("checkout"){

            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/sivagovind586/mrdevops_java_app.git"
            )
            }
        }
        stage ("unit test maven"){
        when{expression { param.action == 'create'} }
            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage ("Integration for maven"){
        when{expression { param.action == 'create'} }
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
        stage ("static code analysis"){
            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }

    }
}