CODE_CHANGES = getGitChanges()
pipeline{
    agent any
    stages{

        stage("build"){
                  when{
                expression{
                    BRANCH_NAME=='master' && CODE_CHANGES == true
                }

            }
            steps{
                echo "Building application"
            }
        }
        stage("test"){
            when{
                expression{
                    BRANCH_NAME=='main'
                }

            }
            steps{
                echo "Testing application"
            }
        }
        stage("deploy"){
            steps{
                echo "Deploying application"
            }
        }                
    }

}
