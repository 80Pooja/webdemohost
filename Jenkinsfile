pipeline {
         agent { label 'slave4' }
        stages {
           stage('checkout') {
                    steps {
                           sh "rm -rf webdemohost"
                           sh "git clone https://github.com/80Pooja/webdemohost.git"
                           sh "cd webdemohost"
                    }
           }
    }
}
