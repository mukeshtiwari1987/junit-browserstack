node {
  echo 'Starting Junit Sample'
  git clone https://github.com/mukeshtiwari1987/junit-browserstack
  browserstack(credentialsId: '2fd5e8fe-90d1-4c78-ba70-9915e5051832') {
       sh 'echo "Printing BrowserStack Credentials"'
       sh 'echo "username is  : "+ $BROWSERSTACK_USERNAME'
       sh 'echo "accesskey is  : "+ $BROWSERSTACK_ACCESS_KEY'
       sh 'echo "local identifier is : "+ $BROWSERSTACK_LOCAL_IDENTIFIER'
       sh 'echo "randome var : "+$ERT_NAME'
       sh 'mvn clean test -P single'
   }
   junit testDataPublishers: [[$class: 'AutomateTestDataPublisher']], testResults: 'target/surefire-reports/TEST-*.xml'
}