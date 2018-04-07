node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: '2e401477-6a37-4f80-af9e-c7d19b68a711', url: 'https://github.com/snasina/python-docker-app.git'
      }
   
   stage('Docker Build') {
     def app = sudo docker.build "saran2250/python-docker-app"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'Docker-ID', url: 'https://hub.docker.com']) {
          sh 'docker tag saran2250/python-docker-app saran2250/python-docker-app:001'
          sh 'docker push saran2250/python-docker-app:001'
          sh 'docker push saran2250/python-docker-app:latest'
      }
    }
   
    stage('App deployed to Docker') {
     echo 'App deployed to Hub..'
    }

   
























}
