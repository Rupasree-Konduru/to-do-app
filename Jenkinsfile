pipeline {
    agent any
   
    environment {
        SCANNER_HOME = tool 'sonar-scanner' // Make sure this tool is configured in Jenkins
    }

    stages {
        stage('git-checkout') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/jaiswaladi246/to-do-app.git'
            }
        }

        stage('Sonar Analysis') {
            steps {
                sh ''' 
                $SCANNER_HOME/bin/sonar-scanner \
                    -Dsonar.url=http://65.0.100.22:9000 \
                    -Dsonar.login=sqp_d57becf08b0699192ea0a89aa204251261332b46 \
                    -Dsonar.projectName=to-do \
                    -Dsonar.sources=. \
                    -Dsonar.projectKey=to-do
                '''
            }
        }
    }
}
