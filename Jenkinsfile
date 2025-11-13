pipeline {
    agent any // Specifies where the pipeline will run (e.g., a Jenkins agent)

    stages {
        stage('Prepare Environment') {
            steps {
                // Jenkins automatically checks out the repository content 
                // into the workspace for the agent.
                echo 'Repository content is checked out by the SCM block.'
                
                // Step 1: Ensure the script is executable
                // This is equivalent to the 'chmod +x' step in GitHub Actions.
                sh 'chmod +x ./time.sh'
            }
        }

        stage('Execute Setup Script') {
            steps {
                // Step 2: Run the shell script
                // This is equivalent to the './setup.sh' step in GitHub Actions.
                // Note: If you used environment variables (like MY_SECRET_KEY), 
                // you would define them in the 'environment' block.
                echo 'Running the setup script...'
                sh './time.sh'
            }
        }
        
        stage('Verification (Optional)') {
            steps {
                // Step 3: List files for verification
                // This is equivalent to the 'ls -la' step in GitHub Actions.
                echo 'Listing workspace files for verification:'
                sh 'ls -la'
            }
        }
    }
}
