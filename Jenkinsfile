pipeline {
 agent any
 environment {
    BUILD = "Hellow this first build"
    TEST =  "hellow this is test build"
    PROD = "hellow this is prod build"

 }
 ansiColor('xterm')
//   parameters {
//         // booleanParam, choice, file, text, password, run, or string
//         booleanParam(defaultValue: true, description: '', name: 'booleanExample')
//         string(defaultValue: "TEST", description: 'What environment?', name: 'stringExample')
//         text(defaultValue: "This is a multiline\n text", description: "Multiline Text", name: "textExample")
//         choice(choices: 'US-EAST-1\nUS-WEST-2', description: 'What AWS region?', name: 'choiceExample')
//         password(defaultValue: "Password", description: "Password Parameter", name: "passwordExample")
//     }
 parameters {
      choice(choices: 'ONE\nTWO', description: 'Choose one or two?', name: 'choiceExample')
 }
   
   options {
                timeout(time: 1, unit: 'MINUTES') 
   }
    stages {
   
     stage('build') {
        steps {
     echo "choiceExample: ${params.choiceExample}"
       }
     }
     stage('test') {
       steps {
        echo "${TEST}"
       }
     }
     stage('prod') {
        steps {
     echo "${PROD}"
        }
     }
}
  post {
   always {
      echo "final execution"
   }
  }
}