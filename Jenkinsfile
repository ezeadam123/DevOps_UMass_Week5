   }

                stage("Code coverage") {
                    try {
                        sh '''
        	            pwd
               		    cd Chapter08/sample1
                	    ./gradlew jacocoTestCoverageVerification
                        ./gradlew jacocoTestReport
                        '''
                    } catch (Exception E) {
                        echo 'Failure detected'
                    }

                    // from the HTML publisher plugin
                    // https://www.jenkins.io/doc/pipeline/steps/htmlpublisher/
                    publishHTML (target: [
                        reportDir: 'Chapter08/sample1/build/reports/tests/test',
                        reportFiles: 'index.html',
                        reportName: "JaCoCo Report"
                    ])                       
                }

                stage("Jacoco checkstyle test"){
                try {
                        sh '''
        	            pwd
               		    cd Chapter08/sample1
                	    ./gradlew checkstyle 
                        '''
                    } catch (Exception E) {
                        echo 'Failure detected'
                    }
                }  
           }
        }
    }
}
