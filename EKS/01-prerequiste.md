
# Prerequisites

##### Tools to be installed beforehand .

##  kubectl

####  Determine whether you already have kubectl installed on your device.

```bash
  kubectl version --client
```

#### To install kubectl run the following command :

```bash
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.29.0/2024-01-04/bin/linux/amd64/kubectl
chmod +x ./kubectl
mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH
```
#### After installing you can verify it's version :

```bash
  kubectl version --client
```

## eksctl

#### To install eskctl runn the following commands :

```bash
# for ARM systems, set ARCH to: `arm64`, `armv6` or `armv7`
ARCH=amd64
PLATFORM=$(uname -s)_$ARCH

curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"

curl -sL "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check

tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz

sudo mv /tmp/eksctl /usr/local/bin

```

## AWS CLI

#### To install aws cli run the following commands :

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install unzip
unzip awscliv2.zip
sudo ./aws/install
```
#### To create an access key

##### 1) Sign into the AWS Management Console.
###### 2) In the top right, choose your AWS user name to open the navigation menu. For example, choose webadmin. Then choose Security credentials.
##### 3) Under Access keys, choose Create access key.
##### 4) Choose Command Line Interface (CLI), then choose Next.
##### 5) Choose Create access key.
##### 6) Choose Download .csv file.


#### To configure AWS CLI use the following commands

##### 1) In a terminal window, enter the following command:

```bash
aws configure
```

##### 2) Enter your AWS credentials. For example:

```bash
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: your-region-name
Default output format [None]: json
```

## Helm 

#### To install helm run the following commands :

```bash
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
sudo apt-get install apt-transport-https --yes
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
```

