pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'])
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    tools{
        maven 'Maven'
    }
    environment {
        NEW_VERSION = 1.0
        // SERVER_CREDENTIALS = credentials('GIT_HUB_CREDENTIALS')
    }
    stages {

        stage ("Git Clone"){
            steps {
                git branch: 'dev', credentialsId: 'github', url: 'https://github.com/anandsingh2733/Project-Git'
                echo "Cloning into GitHub"
            }
        }

        stage ("Git Checkout"){
            steps {
                git branch: 'dev', credentialsId: 'github', url: 'https://github.com/anandsingh2733/Project-Git'
                echo "Checking out into GitHub"
            }
        }

        stage ("build"){
            steps {
                echo 'building the application ....'
                // echo "building version ${NEW_VERSION}"
                build maven
            }
        }

        stage ("test"){
            steps {
                echo 'testing the application ... '
            }
        }

        stage ("deploy"){
            steps {
                echo 'deploying the application ... '
                // echo "deploying with ${SERVER_CREDENTIALS}"
            }
        }
    }
}
