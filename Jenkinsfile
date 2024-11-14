pipeline{
    agent any

    environment{
        NODE_VERIONS = '20.x'
    }

    tools{
        nodejs "${NODE_VERIONS}"
    }

    stage{
        stage('Checkout'){
            steps{
                checkout scm
            }
        }

        stage("Install dependeies"){
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