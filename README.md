![Chef Automate](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chefautomate.PNG)

## Contents
1.	Welcome                                           	
2.	What is chef and what is chef automate.	            
3.	Objective	
4.	Chef server architecture	
5.	Chef Automate Architecture	
6.	Getting Started	


## 1.	Welcome
Welcome to Chef Automate Test drive.
This test drive consists of chef automate and a windows node that is vulnerable to wannacry. You can find for the wannacry vulnerability by running a command. If there is a vulnerability you can remove it using appropriate cookbook using a command.
We can see all this process in chef automate UI.
## 2.	What is chef and what is chef automate.
Chef is a configuration management tool. That means it tries to ensure that the files and software we are expecting to be on a machine are present, configured correctly and working as intended.  We can use chef for one server to thousands of servers to fulfill our requirements. It solves these things by treating infrastructure as a code.
Chef Automate gathers "Compliance", "Workflow" (former Chef Delivery), and "Visibility" concepts. It can be deployed on premise or on Azure.
### "Workflow" 
Workflow allows you to handle continuous deployment pipelines, from development to production. Tests can be performed, and both manual and automatic actions can be taken to progress in the pipeline.
### "Compliance" 
Compliance feature helps you to check whether your nodes are compliant or not with rules. You can define these rules using InSpec or with built-in profiles. Compliance reports are then presented in the UI.
### "Visibility" 
Visibility brings the ability to query Chef data from nodes or server. With this feature, you can, for example, visualize the number of cookbooks deployed on your nodes in the Chef Automate UI.
Finally, Chef Automate integrates with Chef server, which allows management of nodes using cookbooks.
## 3.	Objective
The objective of this test drive is to test the windows machine for wannacry ransomware vulnerability using ‘inspec  exec’. If vulnerability persists it will remove the vulnerability by applying appropriate patches.
## 4.	Chef server architecture
![Chef server architecture](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chefserverarchitecture.png)

## 5.	Chef Automate Architecture
![Chef Automate Architecture](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chefautomatearchitecture.png)

 Once the deployment is done, the template deploys the following resources:
 
.         One chef Automate VM

.         One windows VM with ChefDK

.         NSG’s

.         Public IP’s

.         Storage Account

.         Virtual network.

## 6.	Getting Started

1.	Once you have signed in to Microsoft Test Drive Portal you will see the launch screen as shown below. Now you are ready to launch the test drive by clicking the ‘Start   Free Test Drive’.


a.	To login to the workstation take the public IP, username and password of that machine. Launch the windows RDP client and enter the public IP and click on connect.

![Remote Desktop](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/remotedesktop.png)

b.	After that enter the credentials of the windows system

![Windows System](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/login.png)

c.	You will be launched into the workstation. Go to your favorite browser and type the chef automate url and login with the chef automate user and password.

![Chef Automate URL](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chef-automate-url.png)

d.	You will get the chef automate home page. On that page Click on Nodes tab.

![Chef Automate Homepage](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chef-automate-homepage.png)

e.	The coverge status is good. Go to the compliance status by clicking that tab .

![Chef Compliance Status](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/compliance-status.png)

f.	It looks bad. You can see that The node is non-compliant. To see what was the problem go to that node by clicking the node.

![Chef Non-Compliance Status](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/non-compliant.png)

g.	You can see that the windows machine has the wannacry vulnerability in below screenshot.

![wannacry vulnerability](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/wannacry-vulnerability.png)

h.	Now click the power shell icon to launch the power shell window.

![power shell icon](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/power-shell-icon.png)

i.	To run the Chef commands, we need to redirect to the Chef-repo folder by using cd chef-repo command.

![Chef-repo](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chef-repo.png)

j.	To see the compliance in power shell Run the inspec exec along with the GitHub url that will check for the compliance status.
          
                    > Inspec exec https://github.com/adamleff/inspec-profile-wannacry-exploit.git
    You can see the wannacry vulnerability in power shell also. It looks bad here too.

![wannacry vulnerability powershell](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/wannacry-vulnerability-powershell.png)

![wannacry vulnerability powershell](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/wannacry-vulnerability-powershell1.png)

k.	You saw the Vulnerability in above screenshot. Now you should apply a cookbook to resolve the issue using the command. “Chef-client -o tissues” This cookbook downloads the patches for wannacry vulnerability and installs in our machine.

![Chef-client -o tissues](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chef-client-o.png)

l.	Now, To feel good need run the “inspec exec https://github.com/adamleff/inspec-profile-wannacry-exploit.git” command.

![inspec exec](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/inspec-exec.png)

m.	Run the “chef-client” command to converge the data to automate.

![chef-client](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chef-client.png)

n.	Now, go to the browser again refresh the browser to see the compliance status and see that the windows node is compliant. The below screen shot shows that.

![compliance status](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/windows-node-compliant.png)
