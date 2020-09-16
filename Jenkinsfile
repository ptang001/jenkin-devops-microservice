// DECLARATIVE
pipeline {
    agent any

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