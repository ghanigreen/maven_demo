pipeline {
  agent any
  stages {
    stage('source') {
      steps {
        git(url: 'https://github.com/ghanigreen/maven_demo.git', branch: 'master')
      }
    }
    stage('build') {
      steps {
        bat 'mvn clean install sonar:sonar'
      }
    }
    stage('deploy') {
      steps {
        sh 'cp -r "C:\\Program Files (x86)\\Jenkins\\workspace\\maven_demo\\gameoflife-web\\target\\gameoflife.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 8.5\\webapps"'
      }
    }
  }
}