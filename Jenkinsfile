pipeline {
     agent any
    parameters {
        booleanParam(name:'test-pipe', defaultValue: true, description:'this paramater help you to know project name')
        choice(name: 'namespace', choices:['Dev','Test','Prod'], description: '' ) 
    }
    stages {
            stage('check') {
                steps {
                    echo "checking your code"
                    echo "${params.namespace}"
                }
            }
            stage('test') {
                when {
                    expression{
                        params.test-pipe == true 
                    }
                }
                steps {
                    echo "testing your app" 
                }
            }
            
            stage('deployment') {  
                steps {
                    echo "the code is deployd"
                }
            }    
    }
}
