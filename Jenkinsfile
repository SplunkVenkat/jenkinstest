pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout'
            }
        }
        //stage('Build') {
            //steps {
               // echo 'Clean Build'
               // sh 'mvn clean package'
           // }
        //}
        stage('Sonar') {
            steps {
		 script
		    {
	              if (env.BRANCH_NAME == "master"){
			      sh '''sed -i "4 a sonar.branch.name=$BRANCH_NAME" "$WORKSPACE/sonar-project.properties"'''
                              sh '''sed -i "5 a sonar.branch.target=master" $WORKSPACE/sonar-project.properties'''
			      } else {
			          echo "this is not master"
                             } 
	        sh '''cat $WORKSPACE/sonar-project.properties'''	    
	        echo 'Pulling...' + env.BRANCH_NAME
		    }
               	//def scannerHome = tool 'SonarQube Scanner 3.0'
			   // withSonarQubeEnv('nambasonar') {
				//sh 'mvn clean install sonar:sonar'
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
