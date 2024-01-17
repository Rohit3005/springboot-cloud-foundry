# springboot-cloud-foundry

# PCF--> Pivotal Cloud Foundry

# Three Types of cloud services-->
<b> 1. Plastform as a Service (PaaS) </b>
	Example-> PCF, GCP <br>
  (Managed By you Application, Data) Others are managed by vendors means cloud service <br>

	
2. Infrastructure as a services-->
	Example--> AWS
	(Managed by you Application, Data, Runtime, Middleware) Others are managed by cloud service
	
	
3. Software as a services-->
	Example--> Google Docs
	(All are the component managed by vendors)
	

# These are the component which you need to deployed your application on cloud platform
1.    Application

2.    Data

3.    Runtime

4.    Middleware

5.    Operating system

6.    Virtualization

7.    Servers

8.    Storage

9.    Networking

--------------------------------------------------------------------------------------

	
# Steps:

1.  Install CF-CLI (Cloud Foundry Command Line Interface from below link  
	https://docs.cloudfoundry.org/cf-cli/install-go-cli.html 


2.  Create one Account in Pivotal Cloud Foundry it is free for trial up to 2 GB from below link 
	https://account.run.pivotal.io/z/uaa/sign-up
	
	
3.	Create  spring boot application Add depedency ->
	Spring Web
	Devtool
	lombok
	
4.	Now Pivotal don’t know which war or jar we are going to deploy and its path  and 
	what you want the application name on server and what memory you want to occupy to
	deploy your application on Cloud Foundry  so for that we need to inform all in Cloud 
	foundry using yml file name should be manifest.yml  
	
	manifest.yml -->
	applications:
	-name: <Your application name>
	path: target/<your "jar" file .jar>
	domain: cfapps.io
	memory: <Required memory for application in mb/gb>
	instances: 1
	
5.	Let’s Deploy our application in Pivotal cloud foundry , so for that we need to login in 
	Pivotal using  CF-CLI Cloud Foundry Command line interface so go to the folder where you install 
	your CLI then type command.
	
6.	Then once you open command prompt type command "cf login -a api.run.pivotal.io", 
	then it will ask to enter email id and password which u used on sign up.
	Enter Email Id:
	Password:
	
7.	Then now move to your project directory and open command prompt by pointing path to your  project 

8.	Then type command cf push ,it internally load your manifest.yml , from this file he will get the jar/war
	path then based on memory which u specified memory in yml file , same memory allocation happen on pivotal
	cloud foundry to deploy your application let’s run the command.
	
9.	Now go to pivotal console and sign in again you will find your application is up and running there like 
	below with occupy some space.
	
10.	Now find the Application URL from development section see the right column Route copy that URL then append
	your endpoint URL and hit he URL to check whether our application deploy and working successfully.
	
	Then hit that url instead of localhost.
