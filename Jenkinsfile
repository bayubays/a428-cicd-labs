node {
    stage('Checkout') {
        checkout scm
    }

    stage('Setup Node.js') {
        def nodeHome = tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        env.PATH = "${nodeHome}/bin:${env.PATH}"
    }

    stage('Install Dependencies') {
        sh 'npm install'
    }

    stage('Build') {
        sh 'npm run build'
    }

    stage('Test') {
        sh 'npm test -- --watchAll=false'
    }
}
