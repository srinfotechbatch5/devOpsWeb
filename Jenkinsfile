pipeline{

    agent any

    stages{
        stage('Clone Project'){

            steps{
                git branch: 'feature/2026.02.13', url: 'https://github.com/srinfotechbatch5/devOpsWeb.git'
            }
        }
        stage('Build'){

            steps{

                bat 'mvn clean install'
            }
        }

        stage('Test'){

            steps{

                bat 'mvn test'
            }
        }

        stage('Package'){

            steps{

                bat 'mvn package'
            }
        }


        stage('Generated Artifacts'){

            steps{

                archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }

        stage('Deploy'){

            steps{

                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'TomcatCredentialsNew', path: '', url: 'http://localhost:8080/')], contextPath: 'DevOpsWebApplication', war: 'target/*.war'
            }
        }
    }
}