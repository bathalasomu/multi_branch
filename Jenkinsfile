node('master')
    {
      stage('continuous download')
      {
    git 'https://github.com/selenium-saikrishna/maven.git'
      }
      stage('continuous build')
      {
         
       sh label: '', script: 'mvn package'
    }
    stage('continuous deployment')
    {
        sh label: '', script: 'scp /var/lib/jenkins/workspace/development/webapp/target/webapp.war ubuntu@172.31.29.86:/var/lib/tomcat8/webapps/qaenv.war'
    
      }
      stage('countinuous testing')
      {
          git 'https://github.com/selenium-saikrishna/TestingNew.git'
    
    }
    stage('countinuous delivery') 
    {
        
    sh label: '', script: 'scp /var/lib/jenkins/workspace/development/webapp/target/webapp.war ubuntu@172.31.31.202:/var/lib/tomcat8/webapps/qaenv.war'
    
}}
