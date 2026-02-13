node{
    
    stage('Clone'){
        git branch: 'feature/2026.02.13', url: 'https://github.com/srinfotechbatch5/devOpsWeb.git'
    }
    
    stage('Build'){
        
        bat 'mvn clean install'
    
    }
    stage('test'){
        bat 'mvn test'
    }
    
    stage('published artifacts'){
        archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
    }
}