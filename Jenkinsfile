pipeline {
	//agent { label 'slave2' }
  agent any
 //triggers {
 //     pollSCM '* * * * *'
 // }

  tools {
    maven 'maven-3.9.8' 
  }
  stages {
    stage ('Build') {
      steps {
        sh '''
        	cd ./simple-war 
                cat ./src/main/webapp/index.jsp
        	mvn clean package
        	cd ./target/
        	ls
           '''
      }
    }
    stage ('Deploy') {
      steps {
        script {
          // url: ‘http://<ip_address>:8080/’ –> Your tomcat url
          // contextPath: ‘/pipeline’         –> Context path to deploy in Tomcat
          // onFailure: false                 –> Flag used to control the deployment, 
          //                                     If pipeline Job fails, below deploy block will not run.
          // war: ‘target/*.war’ –> Your war file name
          deploy adapters: [tomcat9(credentialsId: 'webservercred', path: '', url: 'http://52.91.113.154:8080/')], 
                           contextPath: '/preethu-war-1.0.0', 
                           onFailure: false, 
                           war: 'simple-war/target/*-1.0.0.war' 
        }
      }
    }
  }

  // post { 
  //     always { 
  //         cleanWs()
  //     }
  // }

}
