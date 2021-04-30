
pipeline{
    agent any 
    tools {
        maven 'Maven'
    }
    environment {
        NEW_VERSION = '1.3.5'
        SERVER_CREDENTIALS = credentials('server-credential' )
    }                                  
    stages{

        stage ("build"){

            steps {
                echo "Build the application app_name"
                sh "mvn install"
                echo "The new version for this app is ${NEW_VERSION}"
            }
        }

        stage ("test"){
                when {
                    expression {
                        BRANCH_NAME == 'dev'
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
                // withCredentials([
                //     usernamePassword(credentials: 'server-credential', usernameVariable: USER, passwordVariable: PWD)
                //     ]){
                //     sh "Some script ${USER} and ${PWD}"
                // }
            }
        }
    }
}
