pipeline {
  agent any 
  tools {
    maven 'maven'
  }
      stages {
      //stage ('Check-Git-Secrets') {
   //steps {
    //sh 'rm trufflehog || true'
   // sh 'docker run gesellix/trufflehog --json https://github.com/sindhuhack/Devsecops.git > trufflehog'
   // sh 'cat trufflehog'
   // }
//}
      stage ('Source Composition Analysis') {
      steps {
         sh 'rm owasp* || true'
         sh 'wget "https://raw.githubusercontent.com/sindhuhack/github/master/owasp-dependency-check.sh" '
         sh 'chmod +x owasp-dependency-check.sh'
         sh 'bash owasp-dependency-check.sh'
         //sh 'cat /var/lib/jenkins/OWASP-Dependency-Check/reports/dependency-check-report.xml'
        
       publishHTML([allowMissing: true, alwaysLinkToLastBuild: false, escapeUnderscores: false, keepAll: false, reportDir: 'report', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
      }
    }
      }
}
