pipelineJob('Generic Job Example') {
 parameters {
  stringParam('VARIABLE_FROM_POST', '')
 }

 triggers {
  genericTrigger {
   genericVariables {
    genericVariable {
     key("VARIABLE_FROM_POST")
     value("\$.something")
     expressionType("JSONPath") //Optional, defaults to JSONPath
     regexpFilter("") //Optional, defaults to empty string
     defaultValue("") //Optional, defaults to empty string
    }
   }
   genericRequestVariables {
    genericRequestVariable {
     key("requestParameterName")
     regexpFilter("")
    }
   }
   genericHeaderVariables {
    genericHeaderVariable {
     key("requestHeaderName")
     regexpFilter("")
    }
   }
   token('abc123')
   tokenCredentialId('')
   printContributedVariables(true)
   printPostContent(true)
   silentResponse(false)
   shouldNotFlatten(false)
   regexpFilterText("\$VARIABLE_FROM_POST")
   regexpFilterExpression("aRegExp")
  }
 }

 definition {
  cps {
   // Or just refer to a Jenkinsfile containing the pipeline
   script('''
    node {
     stage('Some Stage') {
      println "VARIABLE_FROM_POST: " + VARIABLE_FROM_POST
     }
    }
   ''')
   sandbox()
  }
 }
}
