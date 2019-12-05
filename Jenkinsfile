node ('master')
{
    stage('Cont Download')
    {
        git 'https://github.com/intelliqittrainings/maven.git'
        
    }
            stage('Cont Build')
        {
            sh label: '', script: 'mvn package'
            
        }
        
        stage('Cont Deployment')
        {
          sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/development-1/webapp/target/webapp.war ubuntu@172.31.22.120:/var/lib/tomcat8/webapps/test1.war'
        }
        stage('Cont Testing')
        {
            git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
        }
        stage('Cont Delivery')
        {
            sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/development-1/webapp/target/webapp.war ubuntu@172.31.20.41:/var/lib/tomcat8/webapps/Prod1.war'
        }
        
}
