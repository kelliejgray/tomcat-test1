pipeline {
    agent any
    stages {
        stage('Start Build') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
           }
        }
        stage('checkout class scm') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], \
                doGenerateSubmoduleConfigurations: false, extensions: [], \
                submoduleCfg: [], userRemoteConfigs: [[credentialsId: \
                'kelliejgray1', url: 'https://github.com/kelliejgray/tomcat-test1.git']]])
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'master', credentialsId: 'kelliejgray1', url: 'https://github.com/kelliejgray/tomcat-test1.git'
            } 
        }
        stage('deploy war to tomcat') {
            steps {
                sh 'echo "I will do this no matter what the status is"'sh 'cp $WORKSPACE/*.war /opt/tomcat/tomcat8/webapps'
            }
          }
         }
        }
