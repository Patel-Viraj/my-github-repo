pipeline {
         agent any
         stages {
                //  stage('Check resources') {
                //   steps {
                //       git branch: "main"
                //       url: "git branch: 'main', credentialsId: 'GITHUB_PRIVATE_KEY', url: 'git@github.com:Patel-Viraj/private-repo.git'"    
                //   }
                //  }
                 stage('Configure s3') {
                  steps {
                      sh "aws configure set region $AWS_REGION" 
                      sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY"  
                      sh "aws configure set aws_secret_access_key $AWS_SECRET_KEY"
                  }
                 }
                 stage('copy file to s3') {
                  steps {
                       sh "aws s3 cp index.html s3://production-devops-1"
                   }
                 }
                 stage('Update on CloudFront') {
                  steps {
                       sh "aws cloudfront create-invalidation --distribution-id $CLOUDFRONT_ID --paths '/*'"
                   }
                 }
             
      }
}
