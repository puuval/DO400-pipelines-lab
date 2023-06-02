pipeline {
    agent any
        parameters {
            booleanParam(name: "RUN_INTEGRATION_TESTS", defaultValue: true)
        }

    stages {
        stage('Test') {
            parallel {
                 stage('Integration tests') {
                    when {
                        expression { return params.RUN_INTEGRATION_TESTS }
                    }
                    steps {
                        h './mvnw test -D testGroups=integration'
                    }
                }
            }
        }
    }
}
