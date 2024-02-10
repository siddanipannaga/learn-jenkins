    pipeline {
    agent {
        node {
            label 'AGENT-1'    
        }
    }
    environment { 
        Greeting = 'Hello Jenkins'
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'   
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
               sh """
                echo "Here I wrote shell script"
                echo " $Greeting"
               """
            }
        }
    }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'This runs when pipeline is failed, usually to send some alerst'
        }
        success { 
            echo 'I will say Hello when pipeline is sucess'
        }
    }
}