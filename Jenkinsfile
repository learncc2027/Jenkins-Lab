pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Getting source code from GitHub'
                checkout scm
            }
        }

        stage('Test HTML') {
            steps {
                sh '''
                    echo "Checking index.html..."

                    if [ -f index.html ]; then
                        echo "SUCCESS: index.html exists"
                    else
                        echo "ERROR: index.html missing"
                        exit 1
                    fi

                    grep -q "<h1>Hello from Jenkins!</h1>" index.html

                    if [ $? -eq 0 ]; then
                        echo "SUCCESS: HTML test passed"
                    else
                        echo "ERROR: HTML test failed"
                        exit 1
                    fi
                '''
            }
        }

        stage('Build') {
            steps {
                echo 'Build completed successfully'
            }
        }
    }
}
