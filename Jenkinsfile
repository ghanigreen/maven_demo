node {
stage("scm")
{
git 'https://github.com/ghanigreen/maven_demo.git'
}
stage("unittest"){
bat 'mvn test'
}
stage("build"){
bat 'mvn verify'
}
/*
stage("sonarqube")
{
bat 'mvn sonar:sonar'
}
*/
stage("testresults")
{
junit '**/gameoflife-core/target/surefire-reports/*.xml'
}
stage("archiveartifacts")
{
archiveArtifacts '**/*.war'
}
/*
stage("Deployment")
{
deploy adapters: [tomcat9(credentialsId: 'Tomcat', path: '', url: 'http://localhost:9090/')], contextPath: 'gamepipeline', war: '**\\*.war'
}
*/
}
