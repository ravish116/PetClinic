pipeline {
     agent any
     stages {
         stage ("checkout code") {
             steps {
                 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ravish116/PetClinic.git']]])
             }
         }
         stage ('comile') {
             steps {
                 sh '/opt/devops/apache-maven-3.5.3/bin/mvn compile'
             }
             
         }
         stage ('Test Cases') {
             steps {
                 sh '/opt/devops/apache-maven-3.5.3/bin/mvn test'
             }
         }
         stage ('pakage') {
             sh '/opt/devops/apache-maven-3.5.3/bin/mvn pakage'
         }
     }
}
