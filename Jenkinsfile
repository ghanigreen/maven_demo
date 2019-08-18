node {
stage("scm"){
git 'https://github.com/ghanigreen/maven_demo.git'
}
stage("unittest"){
sh 'mvn test'
}
stage("build"){
sh 'mvn verify'
}
stage("sonarqube")
sh 'mvn sonar:sonar'
stage("testresults")
junit '**/gameoflife-core/target/surefire-reports/*.xml'
stage("archiveartifacts")
archiveArtifacts '**/*.war'
stage("Deployment")
sh label: '', script: 'cp -R /var/lib/jenkins/workspace/anitha_pipeline/gameoflife-web/target/gameoflife.war /opt/tomcat/apache-tomcat-9.0.17/webapps/'
}
