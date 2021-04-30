
pipeline{
    agent any 
        environment {
            NEW_VERSION = '1.3.5'
            SERVER_CREDENTIALS = credentials('server-credentials')
        }
        stages{

            stage ("build"){

                steps {
                    echo "Build the application app_name"
                    echo "The new version for this app is ${NEW_VERSION}"
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
                    echo "deploying with ${SERVER_CREDENTIALS}"
                    sh "${SERVER_CREDENTIALS}"
                }
            }

        }
}
