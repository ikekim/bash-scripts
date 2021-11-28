pipeline {
    agent any

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }

    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }

    stages {
        stage('Build') {
            steps {
                sh 'printenv'
                echo "$GIT_BRANCH"
                sh './hello.sh'
                echo "${params.Greeting} Ike Kim!"
            }
        }

        stage('TFValidate'){
            steps {
                sh 'terraform init'
            }   
        }
    }
}
