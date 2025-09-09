pipeline {
  agent any
  options { timestamps() }
  triggers { pollSCM('H/5 * * * *') } // scheduled polling, 

  stages {
    stage('Build') {
      steps {
        echo 'Task: Compile and package the code.'
        echo 'Tool: Maven'
      }
    }
    stage('Unit and Integration Tests') {
      steps {
        echo 'Task: Run unit tests and integration tests.'
        echo 'Tools: JUnit (unit), REST Assured (integration)'
      }
    }
    stage('Code Analysis') {
      steps {
        echo 'Task: Static code analysis to enforce coding standards and detect code smells.'
        echo 'Tool: Checkstyle'
      }
    }
    stage('Security Scan') {
      steps {
        echo 'Task: Scan dependencies for known vulnerabilities.'
        echo 'Tool: OWASP Dependency-Check'
      }
    }
    stage('Deploy to Staging') {
      steps {
        echo 'Task: Deploy packaged artifact to a staging server.'
        echo 'Tool: Ansible'
      }
    }
    stage('Integration Tests on Staging') {
      steps {
        echo 'Task: Run API integration tests against the staging environment.'
        echo 'Tool: Newman (Postman CLI)'
      }
    }
    stage('Deploy to Production') {
      steps {
        echo 'Task: Deploy the verified artifact to the production server.'
        echo 'Tool: Ansible'
      }
    }
  }
}

