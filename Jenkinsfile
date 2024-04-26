pipeline {
 agent any
 environment {
    BUILD = "Hellow this first build"
    TEST =  "hellow this is test build"
    PROD = "hellow this is prod build"

 }

//   parameters {
//         // booleanParam, choice, file, text, password, run, or string
//         booleanParam(defaultValue: true, description: '', name: 'booleanExample')
//         string(defaultValue: "TEST", description: 'What environment?', name: 'stringExample')
//         text(defaultValue: "This is a multiline\n text", description: "Multiline Text", name: "textExample")
//         choice(choices: 'US-EAST-1\nUS-WEST-2', description: 'What AWS region?', name: 'choiceExample')
//         password(defaultValue: "Password", description: "Password Parameter", name: "passwordExample")
//     }
 parameters {
      choice(choices: 'PROD\nDEV', description: 'Choose PROD or DEV?', name: 'choice')
 }
   
   options {
                timeout(time: 1, unit: 'HOURS') 
   }

    stages {
   
     stage('parameters') {
        steps {
     echo "choice: ${params.choice}"
       }
     }
     stage('PROD') {
       steps {
        echo "${PROD}"
       }
     }
     stage('DEV') {
        steps {
     echo "${DEV}"
        }
     }
}
  post {
   always {
      echo "final execution"
   }
  }
}
