pipeline { 
  agent { 
    kubernetes { 
      inheritFrom 'jenkins-agent-my-app'
    }
  }

  triggers { 
    pollSCM('* * * * *') 
  }

  stages { 
    stage('Test python') { 
      steps { 
        container('python') { 
          sh "pip install -r requirements.txt" 
          sh "python test.py" 
        } 
      } 
    } 
  } 
}
