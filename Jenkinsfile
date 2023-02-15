pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        sh 'g++ main/srn.cpp -o output'
        build 'PES2UG20CS328-1'
        echo 'Successfully Built'
      }
    }
    stage('Test'){
      steps{
        sh './output'
        echo 'Successfully Tested'
      }
    }
    stage('Deploy'){
      when{
        expression{
          currentBuild.result == null || currentBuild.result == 'SUCCESS'
        }
      }
      steps{
        echo 'Deployment Successful'
      }
    }
  }
  post{
    failure{
      echo 'Pipeline failed'
    }
  }
}
  
