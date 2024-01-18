pipeline {
  agent { label 'slave1' } 
  stages {
    stage('checkout') {
      steps {
      sh 'git clone https://github.com/Ahmsagar401/weather-update.git'
      }
    }
    stage('build') {
      steps {
        sh 'mvn --version'
        sh 'mvn clean install'
      }
    }
    stage('Run Locally') {
      steps {
        sh 'java -jar target/home/slave1/workspace/weather_update_Develop/target/weather-forecast-app-1.0-SNAPSHOT.jar &'
        sleep 30
      }
    }
    stage('Deploy') {
      steps {
        sh 'scp /home/slave1/workspace/weather_update_Develop/target/weather-forecast-app-1.0-SNAPSHOT.jar root@172.31.28.235:/opt/apache-tomcat-8.5.98/webapps/'
      }
    }     
  }
}
        
      
    
    
