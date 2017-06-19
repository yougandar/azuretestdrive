![Chef Automate](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chefautomate.PNG)
## Contents
1.	Welcome	3
2.	What is chef and what is chef automate.	3
3.	Objective	3
4.	Chef server architecture	4
5.	Chef Automate Architecture	4
6.	Getting Started	5


## 1.	Welcome
Welcome to Chef Automate Test drive.
This test drive consists of chef automate and a windows node that is vulnerable to wannacry. You can find for the wannacry vulnerability by running a command. If there is a vulnerability you can remove it using appropriate cookbook using a command.
We can see all this process in chef automate UI.
## 2.	What is chef and what is chef automate.
Chef is a configuration management tool. That means it tries to ensure that the files and software we are expecting to be on a machine are present, configured correctly and working as intended.  We can use chef for one server to thousands of servers to fulfill our requirements. It solves these things by treating infrastructure as a code.
Chef Automate gathers "Compliance", "Workflow" (former Chef Delivery), and "Visibility" concepts. It can be deployed on premise or on Azure.
### "Workflow" 
allows you to handle continuous deployment pipelines, from development to production. Tests can be performed, and both manual and automatic actions can be taken to progress in the pipeline.
"Compliance" feature helps you to check whether your nodes are compliant or not with rules. You can define these rules using InSpec or with built-in profiles. Compliance reports are then presented in the UI.
### "Visibility" 
brings the ability to query Chef data from nodes or server. With this feature, you can, for example, visualize the number of cookbooks deployed on your nodes in the Chef Automate UI.
Finally, Chef Automate integrates with Chef server, which allows management of nodes using cookbooks.
## 3.	Objective
The objective of this test drive is to test the windows machine for wannacry ransomware vulnerability using ‘inspec  exec’. If vulnerability persists it will remove the vulnerability by applying appropriate patches.
## 4.	Chef server architecture
![Chef server architecture](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chefserverarchitecture.png)

## 5.	Chef Automate Architecture
![Chef Automate Architecture](https://github.com/yougandar/azuretestdrive/blob/master/chefautomate-images/chefautomatearchitecture.png)

Once the deployment is done, the template deploys the following resources:
•	One chef Automate VM
•	One windows VM with ChefDK
•	NSG’s
•	Public IP’s
•	Storage Account
•	Virtual network.

## 6.	Getting Started

1.	Once you have signed in to Microsoft Test Drive Portal you will see the launch screen as shown below. Now you are ready to launch the test drive by clicking the ‘Start   Free Test Drive’.


a.	To login to the workstation take the public IP, username and password of that machine. Launch the windows RDP client and enter the public IP and click on connect.

b.	After that enter the credentials of the windows system

c.	You will be launched into the workstation. Now clock the power shell icon to launch the power shell window.

d.	Upload the cookbooks that are already in the machine to the chef server using “knife cookbook upload compat_resource audit” command. 

e.	Add those cookbooks to the run list of the client using “knife node run_list add <windows machine name> recipe[audit]” command.

f.	Run the inspec exec along with the github url.
    > Inspec exec https://github.com/adamleff/inspec-profile-wannacry-exploit.git
    You can see the wannacry vulnerability. It looks bad.


g.	Now you must run the “chef-client”
    Then we can see the vulnerability in chef automate.
    
h.	Go to your favorite browser and type the chef automate url, login with the chef automate user and password.

i.	You will get the chef automate home page. Click on node tab.

j.	The coverge status is good. Go to the compliance status by clicking that tab.

k.	It looks bad. The node is non-compliant. To see what was the problem go to that node by clicking the node.

l.	You can see that the windows machine has the wannacry vulnerability.

m.	Now you have to apply a cookbook to resolve the issue using the command. “Chef-client -o tissues”

n.	Now, To feel good need run the “inspec exec https://github.com/adamleff/inspec-profile-wannacry-exploit.git” command.

o.	Run the “chef-client” command to converge the data to automate.

p.	Now, go to the browser again refresh the browser to see the compliance status and see that the windows node is compliant.



