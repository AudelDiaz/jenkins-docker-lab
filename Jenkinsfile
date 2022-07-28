pipeline{
  agent any
  stages {
    stage('query data') {
      steps {
        script {
          sh "curl -k -X GET 'https://api.coindesk.com/v1/bpi/currentprice.json' -o price.json --noproxy '*'"          
        }
      }
    }

    stage('Echo data') {
      steps {
        sh "cat price.json"
      }
    }
  }

  post{
    always{
      archiveArtifacts artifacts: 'price.json', followSymlinks: false, onlyIfSuccessful: false
    }
  }
}
