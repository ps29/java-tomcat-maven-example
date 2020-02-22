pipeline {

  agent {

    label 'master'

  }

  environment {

      
     jobName="hello"
   
    
  }

  stage('Run: Unit test') {

      agent {

        label 'master'

      }
      steps {

        script {

          sh 'ls'

        }
        
      }
    }
  