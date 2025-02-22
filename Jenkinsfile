@Library('java_demo_pipeline@main') _
         
pipeline {
         agent { label 'slave4' }
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64'
        MAVEN_HOME = '/usr/share/maven'
        PATH = "${JAVA_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
    }
        stages {
           stage('checkout') {
                    steps {
                     // sh "rm -rf webdemohost"
                      // sh "git clone https://github.com/80Pooja/webdemohost.git"
                       // sh "cd webdemohost"
                           checkoutcode()  
                    }
           }
                 
                 stage('setupjava17') {
                          steps {
                                   //sh "whoami"
                                   //echo "installing java 17"
                                   //sh "sudo apt update"
                                   //sh "sudo apt install -y openjdk-17-jdk"
                                   setupjava('openjdk-17-jdk')
                          }
                 }
                 stage('setupmaven') {
                 steps {
                         // echo "installing maveen "
                          //sh "sudo apt install -y maven"
                          setupjava('maven')
                 }
        }
          stage('build') {
                    steps {
                          // sh "mvn clean package"
                           builtproject()
                    }
           }
                 stage('publish') {
                    steps {
                           sh "mvn clean deploy"
                          // builtproject()
                    }
           }
           stage('deploy') {
                    steps {
                          sh "sudo cp target/*.war /opt/apache-tomcat-10.1.34/webapps"
                    }
           }
    }
}
