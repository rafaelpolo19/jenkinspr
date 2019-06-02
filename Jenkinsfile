pipeline {
    
    environment {
    registryCredential = 'gitazure2'
    
    }
    agent any

    stages {
        stage('Git') {
            steps {
                script{
                    git "https://github.com/rafaelpolo19/jenkinspr.git"
                }    
            }
        }
        stage('Test') {
            steps {
                script{
                    powershell "C:/Users/jackson.hernandez/scriptjenkins/jenkins.sh"
                    powershell "git remote rm origin"
                    powershell "git remote add origen https://periferiaitgrouptfs.visualstudio.com/DEMO_FABRICA_TD_DEVOPS/_git/jenkinspr"
                    powershell "git remote -v"
             
                    
                }
            }
        }
        stage('Deploy') {
            steps {

                powershell 'git push https://GitJenkins:o64liv5qsxj7vtxhmfkqoq5wm3mmtab7oxhb2qf66c7pskh3ggha@periferiaitgrouptfs.visualstudio.com/DEMO_FABRICA_TD_DEVOPS/_git/jenkinspr --all'                    
                //dpowershell "powershell -Command Remove-Item 'C:/Users/jackson.hernandez/.jenkins/workspace/jenkinspr/*' -Recurse -Force"
        
            }
        }
    }
}
