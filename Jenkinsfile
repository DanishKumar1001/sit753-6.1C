pipeline {
  agent any

  stages {
      stage('Build') {
        steps {
          //Here we can use build tools to build the code and scripts
          
            echo 'Task: Build the code using a build automation tool'
            echo 'Tool: Maven'
        }
      }
      stage('Unit and Integration Tests') {
        steps {
          // here we can use testing frameworks for unit or integration testing using Junit, Selenium, etc tools.
          
            echo 'Task: Run unit tests and integration tests'
            echo 'Tools: JUnit for unit tests, Selenium for integration tests'
        }
      }
      stage('Code Analysis') {
        steps {
          //SonarQube can be used to analyse the code
            echo 'Task: Integrate a code analysis tool'
            echo 'Tool: SonarQube'
        }
      }
      stage('Security Scan') {
        steps {

          // OWASP ZAP or SOnarQUbe can be used for code analysis and security validation 
          
            echo 'Task: Perform a security scan'
            echo 'Tool: OWASP ZAP'
        }
        post {
          success {
              echo 'Security Scan Successful. Sending notification email.'
              emailext to: 'danishkumar1001@gmail.com', subject: 'Security Scan Successful', body: 'The security scan was successful. Logs attached.', attachmentsPattern: '**/*.log', attachLog: true
          }
          failure {
            echo 'Security Scan Failed. Sending notification email.'
            emailext to: 'danishkumar1001@gmail.com', subject: 'Security Scan Failed', body: 'The security scan failed. Logs attached.', attachmentsPattern: '**/*.log', attachLog: true
          }
        }
      }
      stage('Deploy to Staging') {
        steps {

          //here we can implement the deployment script of the application on a staging server on AWS, EC2, etc
            echo 'Task: Deploy the application to a staging server'
            echo 'Tool: AWS CodeDeploy'
        }
      }
      stage('Integration Tests on Staging') {
        steps {

          // here Selenium will test the application for its cirtical prototype integration in staging enviroment
            echo 'Task: Run integration tests on the staging environment'
            echo 'Tool: Selenium'
        }
      }
      stage('Deploy to Production') {
        steps {

          //here we will deploy the application on a live server or a product server
          
            echo 'Task: Deploy the application to a production server'
            echo 'Tool: AWS CodeDeploy'
        }
      }
  }

  post {
    success {
        echo 'Notification: Build Successful. Email sent.'
        emailext to: 'Danishkumar1001@gmail.com', subject: 'Build Successful', body: 'The build was successful. Logs attached.', attachmentsPattern: '**/*.log', attachLog: true
    }
    failure {
        echo 'Notification: Build Failed. Email sent.' 
        emailext to: 'Danishkumar@gmail.com', subject: 'Build Failed', body: 'The build failed. Logs attached.', attachmentsPattern: '**/*.log', attachLog: true
    }
  }
}
