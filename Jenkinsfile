node{
    
    def mavenHome = tool name: "maven3.8.5"
    echo "The job: ${env.JOB_NAME} "
    
    stage('Code Checkout'){
        git branch: 'development', url: 'https://github.com/subarna124/maven-web.git'
    } //end of the checkout 
    
    stage('Build'){
        sh "$mavenHome/bin/mvn clean package"
    } //end of the build
    
    stage ('Nexus'){
        sh "$mavenHome/bin/mvn deploy"
    } //end of nexus
    
    stage('deploy to tomact'){
       sshagent(['credTom']) {
        sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.27.189:/opt/apache-tomcat/webapps/" 
    }
        
        
        
    } //end of tomcat
    
    
} // end of the node
