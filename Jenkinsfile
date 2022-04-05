pipeline {
         agent any
         stages {
                 stage('Copy to S3') {
                  steps {
                      sh "aws s3 cp ./ s3://production-devops-1/"
                      
                      
                  }
                 }
                 stage('build') {
                  steps {
                        echo "App is building"
                   }
                 }
             
      }
}
