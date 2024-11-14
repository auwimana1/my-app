pipeline {
    agent any

 parameters {
        string (name: 'PP1', defaultValue: '1.0.0')
    }

    stages {
        stage("Build and Push image"){
            steps{
                script {
                   // This step should not normally be used in your script. Consult the inline help for details.
                withDockerRegistry(credentialsId: 'ecr:us-east-1:Ade-practice', url: 'https://557195342730.dkr.ecr.us-east-1.amazonaws.com/') {
                    sh "docker build -t Niyela:${params.PP1} ."
                    sh "docker tag Niyela:${params.PP1} 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:${params.PP1}"
                    sh "docker tag Niyela:${params.PP1} 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:latest"
                    sh "docker push 557195342730.dkr.ecr.us-east-1.amazonaws.com/original:latest"
                }

                }

            }
        }
        //stage (){
            //steps{
               // sh "aws ecs update-service  --cluster my-cluster-name  --service  my-service-name  --force-new-deployment"
            }
        }
    
