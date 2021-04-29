CODE_CHANGES = getGitChanges()

pipeline{
    agent any 
        stages{

            stage ("build"){
                // when {
                //     expression{
                //         BRANCH_NAME == 'master' && CODE_CHANGES == true
                //     }
                // }
                steps {
                    echo "Build the application app_name"
                }
            }

            stage ("test"){
                    when {
                        expression {
                            BRANCH_NAME == 'master'
                        }
                    }
                steps {
                    echo "Testing the application app_name"
                }
            }

            stage ("deploy"){
                steps {
                    echo "Deploying the application app_name"
                }
            }

        }
}
