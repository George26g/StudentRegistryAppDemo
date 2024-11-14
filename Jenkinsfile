pipeline{
    agent any


    stage{
        stage('Checkout'){
            steps{
                git branch: 'main', url: "https://github.com/George26g/StudentRegistryAppDemo"
            }
        }

        stage("Install dependences"){
            steps{
                script{
                  
                    bat 'npm install'
                }

            }

        }
        stage("Start application and run tests")
        {
            steps{
                skript{
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8081'
                    bat 'npm test'
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