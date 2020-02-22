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
                sh "java -jar target/dependency/webapp-runner.jar target/*.war || true"
                
            }
            post {
                success {
                    // we only worry about archiving the jar file if the build steps are successful
                    archiveArtifacts(artifacts: 'target/*.jar', allowEmptyArchive: true)
                }
        }

        stage("Production") {
        //when {
          //      environment TEST_PREFIX: "test-IMAGE"
                
           // }
            steps {
                sh "ok"
                
            }

        }
  
    }
}