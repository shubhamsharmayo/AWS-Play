@Library("React") _
pipeline{
    agent{label "jenkin-hook"}

    environment{
        NODE_BIN = '/home/ubuntu/.nvm/versions/node/v26.13.0/bin'
    }

    stages{
        stage("Greetings"){
            steps{
                script{
                waddup()
            }
            }
            
        }

        stage("clone"){
            steps{
                script{
                clone("https://github.com/shubhamsharmayo/AWS-Play","main")
            }
            }
            
        }

        stage("build"){
            steps{
                script{
                build("$NODE_BIN")
            }
            }
            
        }

        stage("deploy"){
            steps{
                script{
                deploy("$NODE_BIN",3000,react)
            }
            }
            
        }
    }
}