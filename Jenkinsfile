pipeline {

agent {
    node{
label 'ps-local'
}
}
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mvn"
    }

 stages {
    //     stage('Build') {
    //         steps {
    //             // Get some code from a GitHub repository
    //           git credentialsId: 'Git-hub', url: "${Repo}"
              
    //             // Run Maven on a Unix agent.
                

    //         }

    //     }
        stage('maven') {
            steps {
        sh "mvn clean install"
            }
        }
    }
}

 stage('Sonar'){
            steps{
                script {
                 withSonarQubeEnv(credentialsId: 'sonar') {
                 sh 'mvn sonar:sonar -Dsonar.projectName=test -Dsonar.projectKey=test'
                }
                }
            }
        }
