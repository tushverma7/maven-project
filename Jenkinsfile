pipeline{
    agent any


    stages{
        stage('SCM Checkout'){
          git 'https://github.com/tushverma7/maven-project.git'
        }
  }
    {
        stage('Compile Stage'){

            steps{
                withMaven(maven : 'mymaven'){
                    sh 'mvn clean compile'
                }
            }
        }

        stage('Testing Stage'){

            steps{
                withMaven(maven : 'mymaven'){
                    sh 'mvn test'
                }
            }
        }


        stage('install Stage'){
            steps{
                withMaven(maven : 'mymaven'){
                    sh 'mvn install'
                }
            }
        }
        
        stage('sonarstage'){
        steps{
             withSonarQubeEnv('soanr')
             withMaven(maven : 'mymaven'){
             sh 'clean package sonar:sonar'
                }
            }
        }

      }
}
