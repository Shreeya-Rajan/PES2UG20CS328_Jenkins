pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        sh 'mvn clean install'
        echo 'Successfully Built'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
        echo 'Successfully Tested'
      }
    }
    stage('Deploy'){
      steps{
        sh 'mvn deploy'
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
  
