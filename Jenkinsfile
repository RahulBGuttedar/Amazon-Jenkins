pipeline {
    agent {lable: 'rahulwinnode'}
      tools {
        maven 'm360'  // This name must match what you configured
    }
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {
            
        stage('pull scm') {
            steps {
                git branch: 'main', url: 'https://github.com/RahulBGuttedar/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }

        
    }

  post{

  success{
     echo 'Build success'
  }
    
  failure{
       echo 'Failure in the build'
   }

  }


}
