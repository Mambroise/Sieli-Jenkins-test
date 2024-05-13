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
    }
}