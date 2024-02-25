pipeline{
    agent any
    parameters{
        string(
            name: 'Student_Name',
            defaultValue: 'Prathmesh',
            description: 'Enter Name of Student.'
        )
        password(
            name: 'Username',
            defaultValue: 'hello@23',
            description: 'Password Hidden.'
        )
    }
    stages{
        stage('Build'){
            steps{
                echo 'Building the application...'
                echo "${params.Username}"
                echo "${params.Student_Name}"
            }
        }
        stage('Test'){
            steps{
                echo 'Testing the application...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying the application...'
            }
        }
    }
    post{
        success{
            echo 'The application has been deployed successfully!'
        }
    }
}
