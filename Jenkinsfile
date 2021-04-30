
pipeline{
    agent any 
    parameters{
        choice( name: 'VERSION', choices : ['1.1.0', '1.2.0', '1.3.0'] , description: 'Yes, it is working' )
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Yes, it is working heheheh' )
    }
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
                echo "mvn install"
                echo "The new version for this app is ${NEW_VERSION}"
            }
        }

        stage ("test"){
                when {
                    expression {
                        params.executeTests
                    }
                }
            steps {
                echo "Testing the application app_name"
            }
        }

        stage ("deploy"){
            steps {
                echo 'Deploying the application app_name'
                echo "deploying with ${SERVER_CREDENTIALS}"
                echo "Deploy version ${params.VERSION}"
            }
        }
    }
}
