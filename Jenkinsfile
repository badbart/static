pipeline {
agent any
stages {
  stage('LintHTML') {
    steps{
    sh 'tidy -q -e *.html'
    }
  }
  stage('Upload to AWS') {
    steps {
      withAWS(region:'us-west-2', credentials:'aws-static') {
        s3Upload(bucket:"udacityjenkinstestabc", file:'index.html', path:'index.html')
    }
  }
}
}
}
