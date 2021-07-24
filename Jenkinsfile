pipeline {
    agent any
    stages {
    stage('Lambda Deploy') {
    steps {
        script {
            def props = readProperties file: 'deploy.properties'
            def environment = props.environment
            map = props.map
            prinln(map)
            
            /*
            withCredentials([
                [credentialsId: "${environment}", $class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']
            ]) {
                sh "aws ecr get-login-password --region $aws_region | docker login --username AWS --password-stdin ${aws_account_id}.dkr.ecr.${aws_region}.amazonaws.com"
                sh "echo 'Updating Dockerfile with Handler: $handler'"
                sh '''sed -i '$ d' Dockerfile'''
                sh "echo 'CMD [\"dist/src/$handler\"]' >> Dockerfile"
                sh "echo 'Displaying Updated Dockerfile content with LAMBDA_FUNC_NAME: $handler'"
                sh '''#!/bin/bash
                      #Stops script if any below command fails
                      set -e
                      cat Dockerfile
                      docker build -t ''' +ecr_repo+''':''' +docker_image_name+''' .
                      docker images
                      docker tag  ''' +ecr_repo+''':''' +docker_image_name+''' ''' +aws_account_id+'''.dkr.ecr.us-east-1.amazonaws.com/''' +ecr_repo+''':''' +docker_image_name+'''
                      docker push ''' +aws_account_id+'''.dkr.ecr.''' +aws_region+'''.amazonaws.com/''' +ecr_repo+''':''' +docker_image_name+'''
                      aws lambda update-function-code --region ''' +aws_region+''' --function-name ''' +lambda+''' --image-uri ''' +aws_account_id+'''.dkr.ecr.''' +aws_region+'''.amazonaws.com/''' +ecr_repo+''':''' +docker_image_name+'''
                '''
                }*/
        }
      }
    }
  }
}
