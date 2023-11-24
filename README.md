# fib-calculator-on-kind

A node.js and Python based apps running on your server!

## Installation

Follow the step-by-step instructions below to install the project:

### Linux Operating System Requirements

To install this project, follow these steps:

1. **For Ubuntu/Debian Distributions:**
   - Clone the project by entering the following command in the terminal:
     ```bash
     git clone https://github.com/egemenyildirim90/kind-helm-fib/
     cd kind-helm-fib
     ```

2. **Required Tools and Software:**
   
 - To install Docker version 24.0.7 on Debian or Ubuntu, you need to follow these steps:

 - Set up the Docker apt repository on your system. You can use the instructions from [Docker Docs](^1^) or the convenience script from [GitHub](^5^).
 - Update the apt package index and install the specific version of Docker Engine. You can use the command `sudo apt-get install docker-ce=24.0.7~3-0~debian-$(lsb_release -cs)` for Debian or `sudo apt-get install docker-ce=24.0.7~3- 
 0~ubuntu-$(lsb_release -cs)` for Ubuntu. You can also check the available versions of Docker Engine with the command `apt-cache madison docker-ce`.
 - Start and enable the Docker service with the commands `sudo systemctl enable docker` and `sudo systemctl start docker`.
 - Optionally, add your user account to the docker group to run Docker commands without sudo. You can use the commands `sudo usermod -aG docker $USER` and `newgrp docker`.

     # Install Kind
     sudo apt-get install kind

     # Install kubectl
     sudo apt-get update
     sudo apt-get install -y kubectl

     # Install Helm
     sudo snap install helm --classic

3. **Run the Project:**
   - You can use the following command to start the project and calculate Fibonacci numbers, for example:
     ```bash
     # Start the project
     kind create cluster --name myfibapp
     
     # Create a POSTGRES SECRET (change '12345' for what you want)
     kubectl create secret generic postgres-password --from-literal=POSTGRES_PASSWORD=12345
     
     # Apply the generated Kubernetes manifests using `kubectl`:
     ```bash
     # Apply Kubernetes manifests
     kubectl apply -f .
     ```
     # Install Ingress Controller (e.g., Nginx)
     ```
     helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
     helm install nginx-ingress ingress-nginx/ingress-nginx
     ```

## Usage
# Run
```bash
kubectl get nodes -o wide
```
Get the Internal IP, you're going to type it into your browser. 
```
kubectl get services
```
Get the Port 80:***** from Load Balancer
Merge them through the browser. For example: 172.10.2.1:31100
You will be able to see the app.

## Contribution

Information on how to contribute to the project...

## Troubleshooting and Frequently Asked Questions (FAQ)

1. **Connection Error:**
   - If you're experiencing a connection error, ensure that Docker and Kind are installed correctly.

2. **Unable to Calculate Fibonacci:**
   - When running the project, make sure you are using the correct API endpoint for Fibonacci calculations.

## License

This project is licensed under [License Name]. For more information, see the [License File](LICENSE)...
