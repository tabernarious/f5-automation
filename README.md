# Automation with F5
This is my first foray into automation with F5. I have many years of in-depth F5 experience across virtually every product and platform, and it is time to dive into automation and how I can:
1. Help people rethink their F5 environments with automation in mind.
2. Help people migrate environments from being manually maintained to using templates, automation, and a centralized source of truth.

Some particularly interesting points that I've found along the way (in the context of F5 environments):
1. Humans have the ability to manage very complex environments with layered and interdependent configurations. This is evident with configurations that share profiles, use child profiles, use human readable naming, and that all exist in one large /Common administrative partition. In fact, in many cases it may be considered more "efficient" (for human use) to reduce the overall configuration size through these tactics.
2. Computers also have the ability to manage very complex environments, but efficiency and reducing errors comes from extreme clarity and low/no interdependency. A computer doesn't care if it has to look at a list of 1000 Client SSL profiles as long as the profiles are consistently named. A computer would likely prefer having 500 Administrative Partitions, each with one or two applications, and no interdependencies. Decommissioning an application would be as easy as deleting the Administrative Partition, and done (mostly).

# Application Services 3 (AS3) Links
* https://devcentral.f5.com/s/articles/AS3-Best-Practice
* [K45530030: Using F5 Modules for Ansible with the F5 Application Services 3 Extension](https://support.f5.com/csp/article/K45530030)
* [Exercise 3.0 - Introduction to AS3](https://clouddocs.f5.com/training/fas-ansible-workshop-101/3.0-as3-intro.html)

# Other Links
* [Class 1: Introduction to Automation & Orchestration](https://clouddocs.f5.com/training/community/programmability/html/class1/class1.html)
* https://devcentral.f5.com/s/articles/demystifying-icontrol-rest-part-1-understanding-the-request-uri
* https://marketplace.visualstudio.com/items?itemName=DumpySquare.vscode-f5-fast
* https://github.com/johnalam/tmsh2JSON/blob/master/AS3_tmpl_export.tcl

# Ansible Links
* [F5 Ansible 101 F5 Workshop](https://clouddocs.f5.com/training/fas-ansible-workshop-101/)
* [Module 3: Deploying AS3 Declarations with Ansible Tower](https://clouddocs.f5.com/training/community/programmability/html/class1/module3/module3.html)
* [F5 Modules for Ansible](https://clouddocs.f5.com/products/orchestration/ansible/devel/)
* https://clouddocs.f5.com/training/fas-ansible-use-cases/
* https://clouddocs.f5.com/training/automation-sandbox/
