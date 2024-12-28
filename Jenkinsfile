node {
  stage('Clone repository') {
         git credentialsId: 'github_access_token', url: 'https://github.com/seokmingg/jenkins-my-diary.git'
        }
  stage('Build image') {
				  
          dir('my-diary-front') {
            dockerImage = docker.build("seokmingg/mydiary-front:2.0")
             }
        }
  stage('Push image') {
         withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
       dockerImage.push()
         }
     }
}
