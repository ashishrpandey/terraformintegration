# terraformintegration
# Objective:
To use packer Terrafrom and Jenkins to automate deployment of an immutable server.


Steps for integration:
1. Create a image using Dockerfile.
	The purpose is to have terraform, packer and git installed at one place

	2. push the image to:  goforgold/build-container:latest

3. Prepare packer.json file nad put it under packer directory

4. 
 Create Ansible Playbook ansible-playbook.yml put it under packer directory 
 
 5.
$ packer validate example.json
Template validated successfully.

6. inside the packer.json 3 povisioners are being used:
Shell provisioner to install Ansible and create project directory home/ubuntu/node-app.
File provisioner to copy project code.
Ansible provisioner to configure our machine.

7. Write jenkinspipeline


Reference :
https://medium.com/@I_M_Harsh/build-and-deploy-using-jenkins-packer-and-terraform-40b2aafedaec
