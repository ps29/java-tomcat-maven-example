#!/usr/local/bin/groovy
pipeline {
    agent { node { label 'master' } }

    environment {
        TEST_PREFIX = "test-IMAGE"
        
    }

    stages {
        
          stage("Compile Package") {
            steps {
                sh "/usr/local/bin/mvn package"
                
                
            }
        }

        stage("Run tests") {
            steps {
                sh "/usr/local/bin/mvn test"
                
            }
          } 
        stage("Deploy") {
            steps {
                sh "java -jar target/dependency/webapp-runner.jar target/*.war "
                
            }
        }
      
    }
}