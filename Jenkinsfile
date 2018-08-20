pipeline {
    agent any
    stages {
        stage('Example') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "admin"
                parameters {
                    choice(name: 'PERSON', choices: ['One', 'Two', 'Three'], description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
        }
        stage(run) {
        when {
            environment ignoreCase: true, name: 'PERSION', value: 'One'
            beforeAgent true
             }
             steps {
                echo 'SUCCESS'
            }
        }
    }
}
