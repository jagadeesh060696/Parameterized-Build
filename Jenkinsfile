pipeline {
    agent any

    parameters {
        string(name: 'APP_VERSION', defaultValue: '1.0.0', description: 'Application version')
        choice(name: 'ENVIRONMENT', choices: ['dev', 'qa', 'prod'], description: 'Target environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests or not')
    }

    stages {
        stage('Show Parameters') {
            steps {
                echo "Version     : ${params.APP_VERSION}"
                echo "Environment : ${params.ENVIRONMENT}"
                echo "Run Tests   : ${params.RUN_TESTS}"
            }
        }

        stage('Run Tests') {
            when {
                expression { params.RUN_TESTS }
            }
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${params.APP_VERSION} to ${params.ENVIRONMENT}"
            }
        }
    }
}
