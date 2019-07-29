pipeline {
    agent any 
    
    
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                dir("/home/durgeshgaur/maven_java_tutorial/NumberGenerator"){
                    
                    sh 'mvn -Dmaven.test.failure.ignore=true -U clean install'
                }
            }
             post {
                success {
                    junit '/home/durgeshgaur/maven_java_tutorial/NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}
