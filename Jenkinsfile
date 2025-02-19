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
                           checkoutcode.groovy()  
                    }
           }
          stage('build') {
                    steps {
                          sh "mvn clean package"
                    }
           }
           stage('deploy') {
                    steps {
                          sh "sudo cp target/*.war /opt/apache-tomcat-10.1.34/webapps"
                    }
           }
    }
}
