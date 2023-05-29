pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/facebook/create-react-app.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test'
      }
    }

   stage('Deploy') {
  steps {
    script {
      def localhost = 'localhost'  // Replace with your localhost server address
      def destination = 'C:\\Users\\musha\\Downloads\\aspdotnetnvcp1\\test2'  // Replace with the desired destination path on your localhost server
      
      sh "rsync -avz build/ ${localhost}:${destination}"
    }
  }
}

  }
}
