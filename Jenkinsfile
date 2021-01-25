node{

   def tomcatWeb = 'C:\\tomcat\\webapps'
   def tomcatBin = 'C:\\tomcat\\bin'
   def mvnHome = 'C:\\maven'
   def tomcatStatus = ''
   
   stage('SCM Checkout'){
      git 'https://github.com/mnreddy69/git-tomcat-pipeline.git'
   }
   
   stage('Compile-Package-create-war-file'){
      // Get maven home path   
      bat "${mvnHome}/bin/mvn clean package"
      }

   stage('Deploy to Tomcat'){
     bat "copy target\\JenkinsWar.war \"${tomcatWeb}\\JenkinsWar.war\""
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         bat "${tomcatBin}\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   }
}
