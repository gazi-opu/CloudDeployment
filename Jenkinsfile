/*pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Jenkins Build Testing....'
      }
    }

  }
} */

pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/gazi-opu/cloud_deployment.git', branch:'main'
      }
    }
   
      stage("Build image") {
            steps {
                script {
                  myapp = docker.build("https://github.com/gazi-opu/cloud_deployment.git#main:service-a")
                }
            }
        }
    /*
      stage("Push image") {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', '24704') {
                            myapp.push("latest")
                            myapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }

    
    /*stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "hellowhale.yml", kubeconfigId: "mykubeconfig")
        }
      }
    }*/

  }

}
