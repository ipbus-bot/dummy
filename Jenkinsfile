node {

   stage('Preparation') { // for display purposes
      sh 'ls'
      // Clean everything
      deleteDir()
      sh 'ls'
      // Get some code from a GitHub repository
      git 'https://github.com/ipbus/ipbb.git'
   }
   stage('Build') {
       sh '''
       echo building
       for k in `seq 20`; do
        echo $k
        sleep 1
       done
       '''
       
   }
   stage('Results') {
      githubNotify account: 'ipbus-bot', repo: 'dummy', credentialsId: '60062b72-b28c-4246-ba6a-fa0daaf9a75a', context: 'pipeline build', description: 'This is a shorted example',  status: 'SUCCESS' 
      sh 'echo done!'
   }
}
