## Objective: To use Packer, Terrafrom, Ansible and Jenkins to automate deployment of an immutable server.


### Steps for integration:

1. Build an image using Dockerfile.
	The purpose is to have terraform, packer and git installed at one place

2. push the image to:  ashishrpandey/terraformintegration:latest

3. Prepare packer.json file nad put it under packer directory

4.  Create Ansible Playbook ansible-playbook.yml put it under packer directory 
 
5. Validate packer file

		$ packer validate example.json
		Template validated successfully.

6. Inside the packer.json 3 povisioners are being used:

	- Shell provisioner to install Ansible and create project directory home/ubuntu/node-app.
	- File provisioner to copy project code.
	- Ansible provisioner to configure our machine.

7. Write jenkinspipeline and trigger the job on jenkins.


With thanks to:
https://medium.com/@I_M_Harsh/build-and-deploy-using-jenkins-packer-and-terraform-40b2aafedaec
