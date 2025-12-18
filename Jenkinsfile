node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("unn-project/u01251219")
         
     }
     stage('Push image') {
         docker.withRegistry('ec2-3-34-181-135.ap-northeast-2.compute.amazonaws.com/', 'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
