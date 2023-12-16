pipeline
{
agent any 
stages{
   stage("Checkout my dit"){
     steps{
      script{
		checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'my-java-JOB-Git-Access', url: 'https://github.com/technospreads/javaSpringBoot.git']])	
        }
       }
     }
     stage("Building Image"){
     steps{
      script{
            sh """
			cd ${WORKSPACE}
			echo "${WORKSPACE}"
			docker build -t "javaspringboot:v1" .
			"""
        }
       }
     }

   }
}
