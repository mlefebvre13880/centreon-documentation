pipeline {
   agent any
   stages {
 
     stage('Install next documentation dependencies') {
       steps {
         echo 'Using Yarn to install dependencies'
         sh 'cd .. && sudo npm cache clean -f && sudo npm install -g n && sudo n latest'
         sh 'yarn install --verbose'
       }
     }
     stage('Build next documentation') {
       steps {
         echo 'Using yarn to build documentation'
       }
     }
     stage('Deploy next documentation release version to dev environment') {
       when { branch 'next' }
       steps {
         sh 'aws s3 sync --delete build s3://centreon-documentation-next/'
         sh 'aws cloudfront create-invalidation --distribution-id E2DXODEFBNUFTG --paths "/*"'
       }
     }
   }
   post {
     always {
       cleanWs()
     }
   }
}
