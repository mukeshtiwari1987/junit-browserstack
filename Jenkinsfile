node {
  echo 'Starting Junit Sample'
  git "https://github.com/mukeshtiwari1987/junit-browserstack"
  browserstack(credentialsId: 'f476a413-e022-43b6-96a4-3b92ed3b556a') {
       sh 'echo "Printing BrowserStack Credentials"'
       sh 'echo "username is  : "+ $BROWSERSTACK_USERNAME'
       sh 'echo "accesskey is  : "+ $BROWSERSTACK_ACCESS_KEY'
       sh 'echo "local identifier is : "+ $BROWSERSTACK_LOCAL_IDENTIFIER'
       sh 'echo "randome var : "+$ERT_NAME'
       sh 'mvn clean test -P single'
   }
   junit testDataPublishers: [[$class: 'AutomateTestDataPublisher']], testResults: 'target/surefire-reports/TEST-*.xml'
}
