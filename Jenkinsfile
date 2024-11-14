pipeline{
    agent any


    stages{
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
                script{
                    bat 'start /b npm start'
                    bat 'start npm test'
                }
            }
        }
         stage("run tests")
        {
            steps{
                script{
                    bat 'start npm test'
                    
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