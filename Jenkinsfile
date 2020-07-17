pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout'
            }
        }
         stage('Build') {
             steps {
                 echo 'Clean Build'
                 sh 'mvn clean package'
            }
         }
        stage('Sonar') {
            steps {
               	def scannerHome = tool 'SonarQube Scanner 3.0'
			     withSonarQubeEnv('nambasonar') {
				sh 'mvn clean install sonar:sonar'
			    }
            }
        }
	//stage('Quality Gate') {
           // steps {
                //timeout(time: 1, unit: 'HOURS') {
                    // Parameter indicates whether to set pipeline to UNSTABLE if Quality Gate fails
                    // true = set pipeline to UNSTABLE, false = don't
                  //  waitForQualityGate abortPipeline: true
                //}
           // }
       // }    
    //}
}
