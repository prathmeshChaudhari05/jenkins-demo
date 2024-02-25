pipeline{
    agent any
    parameters{
        text(
            name: 'CHANGELOG',
            defaultValue: 'This is the default value for text',
            description: 'Enter Name of Student.'
        )
        choice(
            name: 'ENVIRONMENT',
            choices: ['PRODUCTION', 'STAGING', 'DEVELOPMENT'],
            description: 'Select any one.'
        )
        password(
            name: 'API_KEY',
            defaultValue: '123ABC',
            description: 'Password Hidden.'
        )
    }
    stages{
        stage('Deploy'){
            steps{
                when{
                    expression{
                        pramas.ENVIRONMENT == "PRODUCTION"
                    }
                }
                echo "DEPLOYING into PRODUCTION...outside when condition"
            }
        }
        stage('Report'){
            steps{
                // echo "$params.CHANGELOG" > report.txt
                // archiveArtifacts allowEmptyArchive: true, artifacts: '*.txt', followSymlinks: false, onlyIfSuccessful: true
            }
        }
    }
    post{
        success{
            echo 'The application has been deployed successfully!'
        }
    }
}
