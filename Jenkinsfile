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
                    -Dsonar.login=squ_36f9ce22318743243b54f16f066e6664e89fe042 \
                    -Dsonar.projectName=to-do \
                    -Dsonar.sources=. \
                    -Dsonar.projectKey=to-do
                    -X
                '''
            }
        }
    }
}
