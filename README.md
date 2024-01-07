I'm excited to announce the completion of a Deploying Super Mario on Kubernetes.🎮🎮✨🏃‍♂️🎮 🎮

Many people enjoy the classic game Super Mario. We'll look at how to deploy a Super Mario game on Amazon's Elastic Kubernetes Service (EKS) in this guide. We can orchestrate the game's deployment on AWS EKS using Kubernetes, allowing for scalability, reliability, and ease of management.

Go through this blog step by step with screenshots
🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵
https://lnkd.in/dambH3iX
🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵🎮🔵

Prerequisites:🔅
1✅ An Ubuntu Instance
2✅ IAM role
3✅ Terraform should be installed on instance
4✅ AWS CLI and KUBECTL on Instance

LET'S DEPLOY
> STEP 1: Launch Ubuntu instance
1✔ Sign in to AWS Console: Log in to your AWS Management Console.
2✔ Navigate to EC2 Dashboard: Go to the EC2 Dashboard by selecting "Services" in the top menu and then choosing "EC2" under the Compute section.
3✔ launch Instance: Click on the "Launch Instance" button to start the instance creation process.
4✔ Choose an Amazon Machine Image (AMI): Select an appropriate AMI for your instance. For example, you can choose Ubuntu image.
5✔ Choose an Instance Type: In the "Choose Instance Type" step, select t2.micro as your instance type. Proceed by clicking "Next: Configure Instance Details."
6✔ Configure Instance Details:
>>For "Number of Instances," set it to 1 (unless you need multiple instances).
>>Configure additional settings like network, subnets, IAM role, etc., if necessary.
>>For "Storage," click "Add New Volume" and set the size to 8GB (or modify the existing storage to 8GB).
>>Click "Next: Add Tags" when you're done.
⭕Access the EC2 Instance: Once the instance is launched, you can access it using the key pair and the instance's public IP or DNS.

Now clone this Repo. ⬇


STEP BY STEP, CONTINUE 😋😋🎮 🎮
cd Deploying-Super-Mario-on-Kubernetes


sudo chmod +x script.sh
./script.sh
This script will install Terraform, AWS cli, Kubectl, Docker.

Now change directory into the EKS-TF
Run Terraform init
terraform validate
terraform plan
terraform apply --auto-approve
aws eks update-kubeconfig --name EKS_CLOUD --region ap-south-1
cd ..
kubectl apply -f deployment.yaml
#to check the deployment
kubectl get all
kubectl apply -f service.yaml
kubectl get all
kubectl describe service mario-service

Destruction :
Let's remove the service and deployment first
kubectl get all
kubectl delete service mario-service
kubectl delete deployment mario-deployment

Let’s Destroy the cluster
cd EKS-TF
terraform destroy --auto-approve

Paste the ingress link in a browser and you will see the Mario game.
Let’s Go back to 1985 and play the game like children.
We hope the deployment of the iconic Mario game on Kubernetes rekindled your love for gaming. 🎮 🎮
