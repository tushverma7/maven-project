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

stage(deploy to tomcat'){
    steps{
    sshagent(['4d12cf32-6fe7-447a-ae55-fca8b35f12ae']){
    sh 'scp -o -o StrictHostKeyChecking=no */target/*.war ec2-user@13.233.80.96:/var/lib/tomcat/webapps'
}
}
}  

      }
}
