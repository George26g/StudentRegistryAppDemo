pipeline{
    agent any

    environment{
        NODE_VERSION = '20.x'
    }

    tools{
        nodejs "${NODE_VERSION}"
    }

    stage{
        stage('Checkout'){
            steps{
                checkout scm
            }
        }

        stage("Install dependences"){
            steps{
                script{
                    if(isUnix()){
                        sh 'npm install'
                    }
                    else{
                        sh 'npm install'
                    }
                }

            }

        }
        stage("Start application and run tests")
        {
            steps{
                skript{
                    sh 'npm start &'
                    sh 'wait-on http://localhost:8081'
                    sh 'npm test'
                }
            }
        }
    }

    post {
        always{
            echo "CI pipeline completed"
        }
    }
}