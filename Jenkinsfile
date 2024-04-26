pipeline {
 agent any
 environment {
    BUILD = "Hellow this first build"
    DEV =  "hellow this is DEV build"
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
   
   //   stage('parameters') {
   //      steps {
   //   echo "choice: ${params.choice}"
   //     }
   //  when {
   //    ${params.choice} == "PROD"
   //  }
   //   }
   //   when {
   //    expression = "PROD"
   //   }
     stage('PROD_STAGE') {
      when {
      "${params.choice}" == "PROD"
    }
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

