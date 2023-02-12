
node{

def mavenHome = tool name: "maven3.8.5"
    
    stage('checkoutcode'){
        git branch: 'development', url: 'https://github.com/subarna124/maven-web.git'
    } //end of the stage check out code
    
    stage('Build'){
        sh "$mavenHome/bin/mvn clean package"
    } //end of the build stage
  
}
