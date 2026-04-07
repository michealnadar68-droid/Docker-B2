pipeline{
  agent any
  stages{
    stage('#1.Checkout'){
      steps{
        git url:'https://github.com/michealnadar68-droid/Docker-B2/new/main',branch:'main'
      }
    }

    stage('#2.Build the image'){
      steps{
        bat'docker build -t mywebsite .'
      }
    }

    stage('#3. stop all old Containers'){
      steps{
        bat 'docker stop mycont  || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
    
    stage('#4. run the image - containerse'){
      steps{
        bat 'docker run -d -p 4000:80 --name mycont mywebsite'
      }
    }
    
  }
}
