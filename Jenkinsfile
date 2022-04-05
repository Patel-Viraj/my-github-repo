pipeline {
         agent any
         stages {
                //  stage('Check resources') {
                //   steps {
                //       git branch: "main"
                //       url: ""    
                //   }
                //  }
                 stage('Copy to S3') {
                  steps {
                      sh "aws configure set region $AWS_REGION" 
                      sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY"  
                      sh "aws configure set aws_secret_access_key $AWS_SECRET_KEY"
                      sh "aws s3 cp . s3://production-devops-1"
                  }
                 }
                 stage('build') {
                  steps {
                        echo "App is building"
                   }
                 }
             
      }
}
