CODE_CHANGES = getGitChanges()
pipeline{
    agent any
    stages{

        stage("build"){
                  when{
                expression{
                    BRANCH_NAME=='main' && CODE_CHANGES == true
                }

            }
            steps{
                echo "Construiu"
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
