pipeline {
         agent any
         stages {
                 stage('Copy to S3') {
                  steps {
                     sh pwd
                     sh aws --version
                  }
                 }
                 stage('build') {
                  steps {
                        echo "App is building"
                   }
                 }
             
      }
}
