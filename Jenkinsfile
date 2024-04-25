pipeline {
 agent any
 environment {
    BUILD = "Hellow this first build"
    TEST =  "hellow this is test build"
    PROD = "hellow this is prod build"

 }
    stages {
     stage('build') {
        steps {
     echo  ${BUILD}
       }
     }
     stage('test') {
       steps {
        echo ${TEST}
       }
     }
     stage('prod') {
        steps {
     echo ${PROD}
        }
     }
}
}