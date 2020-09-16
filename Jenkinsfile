// DECLARATIVE
pipeline {
        // agent defines where the pipeline will run.
        agent {
            // Here we define that we wish to run on the agent with the label SL202_win
            label "SL202_win"
        }

        // The tools directive allows you to automatically install tools configured in
        // Jenkins - note that it doesn't work inside Docker containers currently.
        tools {
            // Here we have pairs of tool symbols (not all tools have symbols, so if you
            // try to use one from a plugin you've got installed and get an error and the
            // tool isn't listed in the possible values, open a JIRA against that tool!)
            // and installations configured in your Jenkins master's tools configuration.
            maven "MAVEN_HOME"
            jdk "JAVA_HOME"
        }

        environment {
            // Environment variable identifiers need to be both valid bash variable
            // identifiers and valid Groovy variable identifiers. If you use an invalid
            // identifier, you'll get an error at validation time.
            // Right now, you can't do more complicated Groovy expressions or nesting of
            // other env vars in environment variable values, but that will be possible
            // when https://issues.jenkins-ci.org/browse/JENKINS-41748 is merged and
            // released.
            mvnHome = "C:/devel/apps/tools/apache-maven-3.6.3"
        }

	stages {
		stage('Build') {
			steps {
				bat(/"${mvnHome}\bin\mvn" --version/)
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	
	post {
		always {
			echo 'Im awsome. I run always. Hello' 
		}
		success {
			echo 'I run when you are successful' 
		}
		failure {
			echo 'I run when you fail' 
		}
	}
}