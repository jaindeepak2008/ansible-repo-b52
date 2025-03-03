# ansible


### Ansible Manual Command : Using this , we can execute one command at a time.

``` 
    ansible all -i inventory -e ansible_user=centos -e ansible_password=xyz123 -m shell -a "df -h"
```

-i inventory file 
-e extra or environment variables
ansible_user     : speciat variable name for the user-account to use 
ansible_password : speciat variable name for the user-account-password to use 
-m               : name of the module 

Ansible Scripts are referred as Playbooks and playbooks are written using YAML.

YAML : Yet Another Markup Language :

Markup Language : It's a presentation language.

YAML is very simple. Things to be remembered while learning YAML 

``` 
    1) YAML is intendation specific  
    2) YAML is all about Dictionary , List & a Map 
    3) YAML Files should always be ending with either .yml or .yaml 
```

# List 
# A list of tasty fruits
```
    - Apple
    - Orange
    - Strawberry
    - Mango
```

# Dictionary : A Key with a value is referred as Dictionary. 
# An employee record
```
    martin:
        name: Martin D'vloper
        job: Developer
        skill: Elite
```

### Example of list and dictionary 
```
    - martin:
        name: Martin D'vloper
        job: Developer
        skills:
            - python
            - perl
            - pascal
    - tabitha:
        name: Tabitha Bitumen
        job: Developer
        skills:
            - lisp
            - fortran
            - erlang
```
PS : A Key with multiple values is referred as a list 

# Map : A Key with multiple key value pairs is referred as a Object.


### What is a playbook ?
A playbook is a list of plays.

### What is a play ?
A Play is a list of tasks 

### What is a task ? 
A Task is a list of actions that you want to execute.


### Ansible command that we are using to call the playbook

```
 ansible-playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=mongodb robot.yml
 ```


 ### files vs templates 

 Files     : just copy the file as is 
 Templates : Copy the file along with the mentioned variables in the file as a part of the copy 


### Ansible Modules

roles-example/
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── README.md
├── tasks
│   └── main.yml
├── templates
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml 


### Limitation in this project

---> Frontend UI Fails Intermittently ( which ensure you see no items or display of catalogue )


### ansible-pull

```
Whenever the infra is dynamic or not in a position to maintan the static inventory or whenever you want come some config-management to happen as a part of the boot-strapping, prefer using ansible-pull. Ansible-pull expects ansible to be installed on the machine you're running.

So, the easiest option is to install ANSIBLE on the lab ami and keep it ready and prefer this AMI with Ansible as a base image

Ex: ansible-pull-U https_git_repo_url playboon-name.yml 
    ansible-pull -U https://github.com/b52-clouddevops/ansible.git -e COMPONENT=mongodb -e ENV=dev robot-pull.yml

```