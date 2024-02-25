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
                when{
                    expression{
                        params.ENVIRONMENT == "PRODUCTION"
                    }
                }
            steps{
                echo "DEPLOYING into PRODUCTION...outside when the condition"
            }
        }
        stage('Report'){
            steps{
                echo "Started Successfully..."
                writeFile file: 'report.txt', text: "this is the report"
                echo "$params.CHANGELOG"
                echo "Done Successfully..."
                archiveArtifacts allowEmptyArchive: true, artifacts: '*.txt', followSymlinks: false, onlyIfSuccessful: true
            }
        }
    }
    post{
        success{
            echo 'The application has been deployed successfully!'
        }
    }
}
