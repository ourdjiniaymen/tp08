pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'gradle build'
        bat 'gradle javadoc'
        archiveArtifacts 'build/libs/**/*.jar'
        archiveArtifacts 'build/docs/**'
        junit 'build/test-results/test/*.xml'
      }
    }

    stage('Mail Notification') {
      steps {
        mail(subject: 'subject', body: 'test', from: 'ga_ourdjini@esi.dz', to: 'gh_zeggari@esi.dz', replyTo: 'gi_berkane@esi.dz')
      }
    }

  }
}