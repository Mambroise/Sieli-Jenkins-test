pipeline{

    agent any

    stages{

        stage("COUNTINOUS DOWLOAD"){

            steps{
                git branch: 'main', url: 'https://github.com/Mambroise/Sieli-Jenkins-test.git'
            }
        }
        stage("Unit Test"){

            steps{
                sh'mvn test'
            }
        }
        stage("Integration test"){

            steps{
                sh'mvn verify -DskipUnitTests'
            }
        }
        stage("continous Build"){

            steps{
                sh'mvn clean install'
            }
        }
        stage("STATIC TEST ANALISIS"){

            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'nom_d\'appli-sonar-key') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}