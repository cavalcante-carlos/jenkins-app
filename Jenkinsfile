
pipeline{
    agent any 
    environment {
        NEW_VERSION = '1.3.5'
        // SERVER_CREDENTIALS = credentials('server-credentials')
        maven 'Maven'
    }
    stages{

        stage ("build"){

            steps {
                echo "Build the application app_name"
                echo "The new version for this app is ${NEW_VERSION}"
                sh "mvn install"
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
                // withCredentials([
                //     usernamePassword(credentials: 'server-credentials', usernameVariable: USER, passwordVariable: PWD)
                //     ]){
                //     sh "Some script ${USER} ${PWD}"
                // }
            }
        }
    }
}
