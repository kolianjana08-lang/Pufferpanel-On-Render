services:
  - type: web
    name: pufferpanel
    env: ubuntu
    plan: free
    buildCommand: |
      sudo apt update
      sudo apt install -y curl apt-transport-https ca-certificates gnupg lsb-release
      curl -fsSL https://packagecloud.io/pufferpanel/pufferpanel/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/pufferpanel-archive-keyring.gpg
      echo "deb [signed-by=/usr/share/keyrings/pufferpanel-archive-keyring.gpg] https://packagecloud.io/pufferpanel/pufferpanel/ubuntu/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/pufferpanel.list
      sudo apt update
      sudo apt install -y pufferpanel
      sudo pufferpanel user add --email admin@example.com --password admin123 --name Admin
    startCommand: |
      pufferpanel run --port 10000
    envVars:
      - key: PORT
        value: 10000
