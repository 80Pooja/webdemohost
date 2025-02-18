pipeline {
         agent { label 'slave4' }
        stages {
           stage('checkout') {
                    steps {
                           sh "rm -rf webdemohost"
                           sh "git clone https://github.com/80Pooja/webdemohost.git
                           sh "cd webdemohost"
                    }
           }
                  stage('build') {
                    steps {
                            sh "mvn clean package"
                    }
           } stage('deploy') {
                    steps {
                            sh "sudo cp target/*.war https://github.com/80Pooja/webdemohost.git"
                    }
           }
    }
}
