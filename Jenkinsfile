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
        sh 'NODE_OPTIONS=--openssl-legacy-provider npm run build'
    }

    stage('Test') {
        sh 'NODE_OPTIONS=--openssl-legacy-provider npm test -- --watchAll=false'
    }
}
