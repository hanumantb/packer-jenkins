pipeline {
    agent { label 'packer-node' }
    environment {
        // Packer directories
        packer_build_directory = "C:/Users/linux/Documents/packer/"
        packer_exe_path = "C:/Users/linux/Documents/packer/packer.exe"
        // Sets permanent cache location for downloaded isos
        PACKER_CACHE_DIR = "C:/Users/linux/Documents/packer/packer_cache"
    }
    
    stages {
        stage('BaseOS') {
            steps {
                powershell '''
                    C:/Users/linux/Documents/packer/packer.exe build C:/Users/linux/Documents/packer/packer.json
                '''
            }
        }
    }
    post {
        success {
            powershell '''
                Write-Host "Jenkins was successful!"
            '''
            cleanWs()
        }
    }
}
