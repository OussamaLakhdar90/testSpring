
pipeline {
    agent any
     stages {
    stage("Checkout") {
	steps{
bat"dir"
git  branch:'test', url : 'https://github.com/OussamaLakhdar90/testSpring'
bat "dir"}
}
   stage("Build"){
   steps{
bat"mvn compile"
}
   }
   stage ("parallel"){
steps{
parallel testA:{
 echo "Test start"

 echo "sleep 5"
 
 echo "sleep 10"
 
},
testB:{
 
 echo "sleep 4 in B"
}
}
}
}
   post{
   always{
  emailext(
    body: "${env.BUILD_URL}\n${currentBuild.absoluteUrl}",
    to: "always@foo.bar", // Use double quotes for the email address
    recipientProviders: [developers()],
    subject: "${currentBuild.currentResult}'")
	}
}
}
