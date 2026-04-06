pipeline{
  agent any
  stages{
    stage('1.checkout'){
      steps{
        git url:'https://github.com/itsroshravi/DockerB3', branch:'main'
      }
    }

    stage('2.Build Image'){
      steps{
        bat 'docker build -t Mywebsite .'
      }
    }

    stage('3.Stop/Remove old Containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
  stage('4. Run the Image- Containerize'){
    steps{
      bat 'docker run -d -p 5000:80 --name mycont Mywebsite'
    }
  }

    
  }
}
