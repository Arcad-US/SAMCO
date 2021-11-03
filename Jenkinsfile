pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
        disableConcurrentBuilds()
    }
    stages {
        stage('Build ARCAD Version') {
		when { 
			anyOf { 
				branch 'H*'; branch 'R*'; branch 'V*' 
			} 
			not { 
				equals expected: 1, actual: currentBuild.number 
			} 
		}
		steps {
			script {ARCAD_VERSION = env.BRANCH_NAME.substring(0,8)}
            echo "ARCAD Build Starting for $ARCAD_VERSION..."
		}
        }
/*
	stage('Drops Import') {
		when { 
			anyOf { 
				branch 'H*'; branch 'R*'; branch 'V*' 
			} 
			not { 
				equals expected: 1, actual: currentBuild.number 
			} 
		}
		steps {
			script {ARCAD_VERSION = env.BRANCH_NAME.substring(0,8)}
			echo "Drops Import Starting for $ARCAD_VERSION..."
		}
	}
	stage('Deploy to QA') {
		when { 
			anyOf { 
				branch 'H*'; branch 'R*'; branch 'V*' 
			} 
			not { 
				equals expected: 1, actual: currentBuild.number 
			} 
		}
		steps {
			script {ARCAD_VERSION = env.BRANCH_NAME.substring(0,8)}
			echo "Drops Deploy Starting for $ARCAD_VERSION..."
		}
	}
  */
 }
}
