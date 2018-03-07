pipeline {
  agent any
  stages {
    stage('Buiild') {
      steps {
        build 'SampleBuildJob_test'
      }
    }
    stage('Test') {
      steps {
        echo 'PHASE ONE DONE'
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            build 'SampleDeployJob_test'
          }
        }
        stage('') {
          steps {
            build 'Test3A'
          }
        }
      }
    }
    stage('QA') {
      parallel {
        stage('QA') {
          steps {
            build 'Remote_Deployment_to_Cloudera_test'
          }
        }
        stage('') {
          steps {
            build 'SampleTestJob_test'
          }
        }
      }
    }
    stage('UAT') {
      parallel {
        stage('UAT') {
          steps {
            build 'SampleTestJob_test'
          }
        }
        stage('') {
          steps {
            build 'SampleTestJob_test'
          }
        }
      }
    }
    stage('Testing_UAT') {
      steps {
        build 'Test1A'
      }
    }
    stage('Validation') {
      steps {
        build 'Test1A2'
      }
    }
    stage('Production') {
      steps {
        build 'Dhanush_Scal_Test_job1'
      }
    }
  }
}