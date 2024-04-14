node {
    stage ('Check Out') {
        git branch: 'main' , url: 'https://github.com/Bicky7735369355/java-web-app-ashok-it.git'
    }
    stage ('Build Code') {
        def mavenHome= tool name: "Maven-3.8.6" , type: "maven"
        def mavenCMD= "${mavenHome}/bin/mvn"
        sh "${mavenCMD} clean package"
    }  
    stage ('Deploy to container') {
        deploy adapters: [tomcat9(url:'http://34.248.208.195:8080/', credentialsId: 'tomcatCred')] , war: '**/*.war'
    }
    
}