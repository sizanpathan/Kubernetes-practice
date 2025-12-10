# 🐳 **DOCKER — Installation Commands**

---

```bash
curl -fsSL https://get.docker.com -o install-docker.sh
sudo sh install-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
docker --version
docker ps
```

---

# ✔️ **KUBECTL — Installation commands**
```md

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
chmod +x kubectl
sudo cp kubectl /usr/local/bin/kubectl
kubectl version --client

```

# 🚀 **KIND — Creation & Cluster Creation**

---
# 🔧 **Kind Installations**
```bash
# For AMD64 / x86_64
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.30.0/kind-linux-amd64
# For ARM64
[ $(uname -m) = aarch64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.30.0/kind-linux-arm64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
kind version
docker --version
```
# ☸️ **Cluster Creation**
```bash
# Create conig file kind-cluster.yml
kind create cluster --config kind-cluster.yml --name my-cluster
kubectl get nodes
```
# 🛠️ **Istio Installation**
```bash
# TO DOWNLAD ISTIO FILE
curl -L https://istio.io/downloadIstio | sh -
cd istio-1.28.1/bin
sudo cp istioctl /usr/local/bin
# Install Istio using the demo profile, without any gateways
istioctl install -f samples/bookinfo/demo-profile-no-gateways.yaml -y
# Add a namespace label to instruct Istio to automatically inject Envoy sidecar proxies when you deploy your application later
kubectl label namespace default istio-injection=enabled
```
# 📌 **AWS CLI Installation Commands**
```bash
sudo apt-get install unzip
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
```
