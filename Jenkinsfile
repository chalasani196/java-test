pipeline {
    agent any

    environment {
        function_name = 'jenkins-007'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                sh 'mvn package'
            }
        }

    stages {
          stage("SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('mysonar') {
                sh 'mvn sonar:sonar'
              }
            }
          }
        
        }
      }
    }


        // stage('Push') {
        //     steps {
        //         echo 'Push'

        //         sh "aws s3 cp target/sample-1.0.3.jar s3://jenkins-007"
        //     }
        // }

//         stage('Deploy') {
//             steps {
//                 echo 'deploy'

//                 sh "aws lambda update-function-code --function-name $function_name --region us-east-1 --s3-bucket jenkins-007 --s3-key sample-1.0.3.jar"
//             }
//         }
//     }
    
