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
"Workflow" allows you to handle continuous deployment pipelines, from development to production. Tests can be performed, and both manual and automatic actions can be taken to progress in the pipeline.
"Compliance" feature helps you to check whether your nodes are compliant or not with rules. You can define these rules using InSpec or with built-in profiles. Compliance reports are then presented in the UI.
"Visibility" brings the ability to query Chef data from nodes or server. With this feature, you can, for example, visualize the number of cookbooks deployed on your nodes in the Chef Automate UI.
Finally, Chef Automate integrates with Chef server, which allows management of nodes using cookbooks.
## 3.	Objective
The objective of this test drive is to test the windows machine for wannacry ransomware vulnerability using ‘inspec  exec’. If vulnerability persists it will remove the vulnerability by applying appropriate patches.

