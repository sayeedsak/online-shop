node{

    stage('SCM Checkout')
    {
        git url: 'https://github.com/sayeedsak/online-shop.git'
    }
    
    stage('Run Docker Compose File') { 
        withCredentials([usernamePassword(credentialsId: 'local-pass', usernameVariable: "myuser", passwordVariable: "mypass")]) {
            sh 'sshpass -p "${mypass}" | sudo -S docker compose build' 
            sh 'sshpass -p "${mypass}" | sudo -S docker compose up -d' 
        } 
    }
  stage('PUSH image to Docker Hub')
    {
      /* withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u upasanatestdocker -p ${DHPWD}"
        }
        sh 'docker push vardhanns/phpmysql_app'
        */
        //docker.withRegistry( 'https://registry.hub.docker.com', 'DockerHubPassword' ) {
             
             sh 'sudo docker login -u "upasanatestdocker" -p "Zephyr@17" docker.io'
             //sh 'sudo docker push upasanatestdocker/mysql'
             //sh 'sudo docker push upasanatestdocker/job1_web1.0'
             sh 'sudo docker push upasanatestdocker/job1_web2.0'
            // sh 'docker push upasanatestdocker/mysql'
          
    }
}
