pipeline{
  agent any
  stages{
  
    stage('Checkout'){
      steps{
      	git branch: 'main', url: 'https://github.com/KaustubhBhor11/model_train.git'
      }
    }
    
    stage('Install Dependencies'){
      steps{
        sh 'pip3 install -r requirements.txt'
      }
    }
    
    stage('Train model'){
      steps{
        sh 'python3 train.py'
      }
    }
    
    stage('Test model'){
      steps{
        sh 'python3 test.py'
      }
    }
    
    stage('Archive model'){
      steps{
        archiveArtifacts artifacts: 'model.pkl',fingerprint:true
      }
    }
  }
}
      
