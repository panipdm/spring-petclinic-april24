pipeline  {
  agent  {lavel 'spc'}
  stages  {
    stage  ('git'){
	  steps  {
	    git url: 'https://github.com/panipdm/spring-petclinic-april24.git',  branch: 'main'
	  }
	}
	stage  ('build')  {
	  steps  {
	    mail bcc: '', body: 'Build Started', cc: '', from: '', replyTo: '', subject: 'Build Started', to: 'panipdm.in'
	    sh 'mvn clean package'
		junit testResults: '**/surefire-reports/*.xml'
		archive '**/target/spring-petclinic-*.jar'
		mail bcc: '', body: 'Build Completed', cc: '', from: '', replyTo: '', subject: 'Build Completed', to: 'panipdm.in'
	  }
	
	}
  }

}
