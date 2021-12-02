node {
    stage ('git')
    {
    git 'https://github.com/ghanitutorsbot/maven_demo.git'
    }
    stage ('build')
    {
    bat 'mvn install'
    }
    stage ('deploy')
    {
    deploy adapters: [tomcat9(credentialsId: '19d15899-b120-4d8b-a8f9-999f33ed58d4', path: '', url: 'http://localhost:8081/')], contextPath: 'scriptedscmapp', war: '**/*.war'
    }
}
