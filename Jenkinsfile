pipeline {
    agent any


    tools {
        nodejs "node" 
    }

    stages {
        stage("Test") {
            steps {
                git branch: "main",
                    url: "https://github.com/cuongntblockhive/jenkins.git"
                sh 'npm install'
                sh 'npm test'
            }
        }
        stage("Deploy") {
            steps {
                sh '''
                    # Install VPN software (example: OpenVPN)
                    apt-get update
                    apt-get install -y openvpn

                    # Configure VPN credentials and connection
                    echo "VPN_USERNAME=Archaic.Cuong" >> vpn-config.env
                    echo "VPN_PASSWORD=Ax9slHb4$s" >> vpn-config.env

                    # Establish VPN connection
                    openvpn --config vpn-config.env --daemon

                    # Wait for the VPN connection to be established
                    sleep 10

                    # Check VPN connection status
                    if [[ $(pgrep -x openvpn) ]]; then
                        echo "VPN connection established successfully"
                    else
                        echo "Failed to establish VPN connection"
                        exit 1
                    fi
                '''
            }
        }
    }
}