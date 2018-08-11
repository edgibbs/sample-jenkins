buildMaster()

def buildMaster() {
  node() {
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
}

def checkoutStage() {
  stage('Checkout') {
    deleteDir()
      checkout scm
  }
}

def sayHelloStage() {
  stage('Hello') {
    sh "echo 'Hello'"
  }
}

def cleanupStage() {
  stage('Cleanup') {
    cleanWs()
  }
}
