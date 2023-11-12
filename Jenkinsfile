pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/Documents/GitHub/JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP Dependency-Check Vulnerabilities') {
      steps {
        dependencyCheck additionalArguments: ''' 
                    -o './'
                    -s './'
                    -f 'ALL' 
                    --prettyPrint''', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
        
        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
      }
    }
	}	
}
