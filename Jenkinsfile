pipeline{
    agent any
    environment{
        PATH ="$PATH:/opt/apache-maven-3.9.8/bin"
    }
    stages{
        stage('Get Code'){
            steps{
              git 'https://github.com/mark-1010/jenkin-java-test.git' 
            }
        }
        stage('Build'){
            steps{
              sh "mvn clean package"
            }
        }
        stage('sonarQube analysis'){
            steps{
                withSonarQubeEnv('Sonar-Server-7.8'){
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
