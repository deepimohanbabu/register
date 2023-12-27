pipeline {
    agent { label 'Jenkins-agent' }
    tools {
        jdk 'java 17'
        maven 'maven 3'
    }
    stages { 
        stage("Cleanup workspace") {
               steps {
               cleanWs()
               }
        }
        stage("Checkout from SCM") {
               steps {
                    git branch: 'main', credntialsId: 'github', url: 'https://github.com/deepimohanbabu/register.git'
                }
        }

       stage("Build application") {
          steps {
              sh "mvn clean package"
              }
       }
       stage("Test application") {
             steps {
                  sh "mvn test"
             }
       }

    }
}
