pipeline {

  agent {

    label 'master'

  }

  environment {

      
     jobName="$JOB_NAME"
   
    
  }

  stage('Run: Unit test') {

      agent {

        label 'master'

      }
      steps {

        script {

          sh '/home/jenkinsbot/plugin/scripts/jenkins/scripts/unittest.sh'

        }
        
      }
    }
  