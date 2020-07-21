pipeline {
    agent none
    stages {
	stage('Build Stage') {
	    agent {
                        label "master"
                }
        steps {
                echo 'This stage will be build first'
                bat 'Build.bat'
                }
        }

	
        stage('Test Job') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Task1 on Agent"
                           bat 'Unit.bat'
                    }
                    
                }
                stage('Deploy Job') {
                    agent {
                        label "master"
                    }
                    steps {
						   bat 'Deploy.bat'
					}
                }
            }
        }
    }
}
