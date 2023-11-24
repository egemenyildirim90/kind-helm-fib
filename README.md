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
     
  ## Install Docker 24.0.7
 - Set up the Docker apt repository on your system. You can use the instructions from [Docker Docs](^1^) or the convenience script from [GitHub](^5^).
 - Update the apt package index and install the specific version of Docker Engine. You can use the command `sudo apt-get install docker-ce=24.0.7~3-0~debian-$(lsb_release -cs)` for Debian or `sudo apt-get install docker-ce=24.0.7~3- 
 0~ubuntu-$(lsb_release -cs)` for Ubuntu. You can also check the available versions of Docker Engine with the command `apt-cache madison docker-ce`.
 - Start and enable the Docker service with the commands `sudo systemctl enable docker` and `sudo systemctl start docker`.
 - Optionally, add your user account to the docker group to run Docker commands without sudo. You can use the commands `sudo usermod -aG docker $USER` and `newgrp docker`.

  ## Install Kind 0.12.0

- Install kind with the command `go install sigs.k8s.io/kind@v0.12.0`. This will put kind in `$(go env GOPATH)/bin`. You may need to add that directory to your `$PATH` as shown [here](^3^) if you encounter the error `kind: command not found` after installation.
  
## Install kubectl Client Version: v1.28.3

- Determine your operating system and architecture. You can use the command `uname -a` on Linux or `systeminfo` on Windows to get this information.
- Download the kubectl binary for your system from the [Kubernetes release page](^5^). For example, if you are using Linux x86-64, you can use the command `curl -LO https://dl.k8s.io/release/v1.28.3/bin/linux/amd64/kubectl`. If you are using Windows x86-64, you can use the command `curl.exe -LO https://dl.k8s.io/release/v1.28.3/bin/windows/amd64/kubectl.exe`.
- Make the kubectl binary executable and move it to a directory in your PATH. For Linux, you can use the commands `chmod +x ./kubectl` and `sudo mv ./kubectl /usr/local/bin/kubectl`. For Windows, you can use the commands `icacls .\kubectl.exe /grant Everyone:F` and `move .\kubectl.exe %USERPROFILE%\bin\kubectl.exe`.
- Verify that kubectl is installed and has the correct version. You can use the command `kubectl version --client` to check the client version. You should see something like this:

```
Client Version: version.Info{Major:"1", Minor:"28", GitVersion:"v1.28.3", GitCommit:"2e7996e3e2712684bc73f0dec0200d64eec7fe40", GitTreeState:"clean", BuildDate:"2023-06-01T12:59:06Z", GoVersion:"go1.17.2", Compiler:"gc", Platform:"linux/amd64"}
```

## Install Helm
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
