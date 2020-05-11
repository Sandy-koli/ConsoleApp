node('DOTNETCORE') {
    stage('SCM'){
        checkout([$class: 'GitSCM', 
        branches: [[name: '*/master']], 
        doGenerateSubmoduleConfigurations: false, 
        extensions: [], 
        submoduleCfg: [],
        useRemoteConfigs: [[url: 'https://github.com/Sandy-koli/ConsoleApp']]])
    }
     stage('Build'){
        sh 'donet build ConsoleApp1'
    }
     stage('Test'){
        echo 'Execute Unit Test'
    }
    stage('Package'){
        exho 'Zip it up'
    }
     stage('Deploy'){
        echo 'Push to deployment'
    }
}
