# CICD_pipeline2_ci_ansible
 
renamed master to main
list repos:
this = https://github.com/johnmogi/CICD_pipeline1_IAc_plan-files

make sure to add hosts file

[PROD]
prodvm1 ansible_host=<subnet> ansible_port=<port> ansible_user=<user> ansible_password=<pass>
prodvm2 ansible_host=<subnet> ansible_port=<port> ansible_user=<user> ansible_password=<pass>
prodvm3 ansible_host=<subnet> ansible_port=<port> ansible_user=<user> ansible_password=<pass>
[STAG]
stagvm1 ansible_host=<subnet> ansible_port=<port> ansible_user=<user> ansible_password=<pass>
stagvm1 ansible_host=<subnet> ansible_port=<port> ansible_user=<user> ansible_password=<pass>

PROJECT
Introduction
For the last few weeks we have been using terraform to provision the infrastructure of our application and we are using ansible to automate the deployment process, which is quite respectable but not enough. This week we will finish automating the entire process by using CI/CD methodologies to orchestrate the use of both tools and deploy the changes made to the code continuously and automatically.

Project Overview
This week’s project consists of using Azure Pipelines to configure a complete CI/CD pipeline for the WeightTracker application that includes building the application and deploying it into (an existent) infrastructure. As a bonus we are going to create an additional CI/CD pipeline to automate the infrastructure updates when our Terraform code changes.

# ansible playbook instructions

hello and welcome to the world of ansible

[]: # Language: YML
[]: # Path: deploy_files/play.yml
[]: # Path: deploy_files/README.md

At the server side, run the following command:

```

# staging - check if the servers are running:
Staging public ip: 20.124.5.101
ping 10.0.20.4
ping 10.0.20.5

# production - check if the servers are running:
prod public ip: 20.124.177.159
ping 10.0.20.4
ping 10.0.20.5
ping 10.0.20.6

you'll need to provide the psecret key for each of the servers:
<pre>
psecret.yml:
PIP : < public ip staging or production >
COOKIE : < okta cookie >
ENV : production
PHOST : < http://${ PIP }:8080 >
PUSER : < postgres username >
PDB : <postgres database server name >
PPASS : < postgres password >
PPORT : < postgres port >
PKTA : < okta dev domain ip as in dev-123456.okta.com > // in this exact format
OCLIENT : < okta client >
OSECRET : < okta secret >
</pre>

```

now you are ready to run the playbook:
ansible-playbook play.yml

will run over the required steps tp install application configuration over your server fleet.
I hope you enjoy the experience.

automation issue tracker
moving ansible to base path dir - succeded?

<pre>
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/adminuser/.local/bin:/home/adminuser/.local/bin/ansible:/home/adminuser/.local/bin/ansible

/home/adminuser/.local/bin:/home/adminuser/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
</pre>
