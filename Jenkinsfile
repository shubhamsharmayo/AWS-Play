@Library("React") _
pipeline{
    agent{label "jenkin-hook"}

    environment{
        NODE_BIN = '/home/ubuntu/.nvm/versions/node/v26.13.0/bin'
    }

    stages{
        stage("Greetings"){
            script{
                waddup()
            }
        }

        stage("clone"){
            script{
                clone("https://github.com/shubhamsharmayo/AWS-Play","main")
            }
        }

        stage("build"){
            script{
                build("$NODE_BIN")
            }
        }

        stage("deploy"){
            script{
                deploy("$NODE_BIN",3000,react)
            }
        }
    }
}