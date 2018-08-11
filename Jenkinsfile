def buildMaster() {
  try {
    checkoutStage()
    sayHelloStage()
  } catch(Exception exception) {
    currentBuild.result = "FAILURE"
    throw exception
  } finally {
    cleanupStage()
  }
}

def checkoutStage() {
  stage('Checkout') {
    deleteDir()
      checkout scm
  }
}

def sayHelloStage() {
  sh "echo 'Hello'"
}

def cleanupStage() {
  stage('Cleanup') {
    sh "docker-compose down"
      cleanWs()
  }
}
