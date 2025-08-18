@Library("Shared") _
pipeline{
    agent any
    
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                    name("manoj")
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    gitClone("https://github.com/LondheShubham153/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                dockerBuild("notes-app","latest","trainwithshubham")
            }
        }
        stage("Push to Dockerhub"){
            steps{
                script{
                    dockerPush("notes-app","latest","trainwithshubham")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deploying code"
                //sh "docker compose up -d"
            }
        }
    }
}
