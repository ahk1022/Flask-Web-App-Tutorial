@Library("shared") _
pipeline{
    
    agent { label "ahk" }
    
    
    stages{
        stage("code"){
            
            steps{
                
                echo "code cloning"
                script{
                    clone("https://github.com/ahk1022/Flask-Web-App-Tutorial.git","main")
                }
            }
        }
        stage("build"){
            steps{
                
                echo "code build"
                docker_build("web-app","latest","ahk3983")
                   
            }
        }
        stage("Pust to DockerHub"){
            
            steps{
                script{
                    
                    docker_push("web-app","latest","ahk3983")
                }
            }
        }
        stage("deploy"){
            steps{
                
                echo "deploy stage"
                sh "docker compose up"
            }
        }
    }
    
}
