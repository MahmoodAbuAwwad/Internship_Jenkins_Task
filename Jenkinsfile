pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
        echo "====== Checkout Github Repo. ======"
        git credentialsId: 'github', url: 'https://github.com/MahmoodAbuAwwad/Internship_Jenkins_Task.git'        
        sh "git checkout master"
      }
    }
    stage("CreatingScript"){
      steps{
        echo "===== Creating Build_number.tar.gz ====="
        sh "chmod +x build_number.sh"
        sh "tar -cvf ${currentBuild.number}.tar.gz build_number.sh"
        sh "ls"
        sh "git add ."
        sh "git commit -m 'create tar file'"
        sh "git push origin master"
      }
    }
  }
}
