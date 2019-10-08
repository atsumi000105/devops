# DevOps Interview Questions

<p align="center">"<i>DevOps is not a goal, but a never-ending process of continual improvement.</i>" - Jez Humble</p>

****

:information_source: &nbsp;This repository contains interview questions on various DevOps related topics

:bar_chart: &nbsp;There are currently **111** interview questions

:warning: &nbsp;Some answers might be only partial and shouldn't be used as they are in interviews

:pencil: &nbsp;You can add more questions & answers by submitting pull requests :)

****

## Table of Contents

  1. [DevOps](#devops)
  1. [Jenkins](#jenkins)
  1. [AWS](#aws)
  1. [Network](#network)
  1. [Linux](#linux)
  1. [Ansible](#ansible)
  1. [Terraform](#terraform)
  1. [Containers](#containers)
  1. [Docker](#docker)
  1. [Kubernetes](#kubernetes)
  1. [Python](#python)
  1. [Prometheus](#prometheus)
  1. [Git](#git)
  1. [Scenarios](#scenarios)


## DevOps

###### beginner

* What is Continuous Integration?
* What is Continuous Deployment?
* What is Continuous Delivery?

* What DevOps helps us to achieve?
* What do you consider as best practices for CI/CD?
* What are the anti-patterns of DevOps?

* Which DevOps tools you consider as top tools? Which tools have you worked with?
* What systems and/or tools are you using for the following?:

  * CI/CD
  * Provisioning infrastructure
  * Configuration Management
  * Monitoring & alerting
  * Logging
  * Code review
  * Code coverage
  * Tests

* What is the difference between SQL and NoSQL?
* What the difference between VPN and VPS?
* What is the difference between SSH and SSL?

* What scripting language are you familiar with? why specifically this one?
* Describe some of the scripts you have written. What are they used for? how long did it take you to write them?
* How long do you think it would take you to learn another language?

##### Intermediate

* Tell me how you perform plan capacity for your CI/CD resources (e.g. servers, storage, etc.)
* How would you structure/implement CD for an application which depends on several other applications?
* How do you manage dependencies?

* Explain what are design patterns. Which design patterns are you familar with?

##### advanced

* How do you measure your CI/CD quality? Are there any metrics you are using?
* What is a configuration drift? What problems is it causing?

```
Configuration drift happens when in an environment of servers with the exact same configuration and softwares a certain server
or servers are being appied with updates or configuration which other servers don't get and over time these servers become
slightly different than all others.

This situtation might lead to bugs which hard to identify and reproduce.
```

* How to deal with configuration drift?
* In what scenarios would you prefer to use SQL?
* In what scenarios would you prefer to use NoSQL?


## Jenkins

###### beginner

* Explain what is Jenkins and what is it used for
* Explain each of the following in the context of nodes:
  * Master
  * Slave
  * Executor
  * Agent
  * Label
* Explain each of the following in context of jobs:
  * Job
  * Build
  * Test
  * Artifacts
* Explain the architecture of Jenkins
* What are the different ways to trigger a build?
* How do you start a build automatically upon a change in a certain repository?
* What is a plugin?
  * What plugins are you using in Jenkins? Which do you consider to most useful?
* Installation questions
  * How to install Jenkins?
  * How to install a plugin?
  * How to install an agent?
* Explain CI/CD and how you implemented in Jenkins

###### Intermediate

* What type of jobs there are? what is the advantage of each type?
* What ways are you familiar with to notify users on build results?
* How to secure Jenkins?

###### Advanced

* Write a script to remove all the jobs which include the string "REMOVE_ME"



## AWS

###### Global Infrastructure

- Explain the following
  - Availability zone
  - Region
  - Edge location

###### S3 - beginner

* Explain what is S3 and what is it used for
* What is a bucket?
* True or False? a bucket name must be globally unique
* What objects in S3 consists of?
  * Another way to ask it: explain key, value, version id and metadata in context of objects
* Explain data consistency
* Can you host dynamic websites on s3? what about static websites?
* What security measures have you taken in context of S3?

###### CloudFront

* Explain what is CloudFront and what is it used for
* Explain the following
  * Origin
  * Edge location
  * Distribution
* What delivery methods available for the user with CDN?
* True or False? object are cached for the life of TTL


###### EC2 - beginner

* What type of instances have you created?
* How to increase RAM for a given EC2 instance?


## Network

Network questions can be found [here](https://github.com/bregman-arie/computer-networking/blob/master/interview_questions/README.md)


## Linux

##### beginner

* Explain what each of the following commands does and given an example on how to use it
  * ls
  * rm 
  * rmdir (can you achieve the same result by using `rm`?)
  * grep
  * wc
  * df

* How to make sure a service will start on a OS of your choice?

* How do you schedule tasks periodically?

* How to change the permissions of a file?

* What does the following permissions mean?:
  * 777
  * 644
  * 750

* How to add a new user to the system without providing him the ability to log-in into the system?

* What commands are you using for troubleshooting issues? specifically:
  * Disk issues
  * Memory, CPU issues
  * Networking issues

* What is the difference between Linux and Unix?

* What is a Linux kernel module and how do you load a new module?

* What is KVM?

* Explain what would be the result of each command:

```
echo $0
echo $?
echo $$
echo $@
echo $#
```

* How to grep two strings?

* What is the different between a soft link and hard link?

```
hard link is the same file, using the same inode.
soft link is a shortcut to another file, using a different inode.

soft links can be created between different file systems while
hard link can be created only within the same file system.
```

* How to run a process in the background and why to do that in the first place?
```
You can achieve that by specifying & at end of the command.
As to Why? since some commands/processes can take a lot of time to finish
execution or run forever
```

* What signal is used when you run 'kill <process id>'?
```
The default signal is SIGTERM (15). This signal kills
process gracefully which means it allows it to save current
state configuration.
```

* What signals are you familiar with?
```
SIGTERM - default signal for terminating a process
SIGHUP - common usage is for reloading configuration
SIGKILL - a signal which cannot caught or ignored

To view all available signals run `kill -l`
```

* In what state a process in Linux can be?

```
Ready
Running
Blocked
Terminated
Zombie
```


## Ansible

* Describe each of the following components in Ansible, including the relationship between them:
  * Task
  * Module
  * Play
  * Playbook
  * Role

```
Task – a call to a specific Ansible module
Module – the actual unit of code executed by Ansible on your own host or a remote host. Modules are indexed by category (database, file, network, …) and also referred as task plugins.

Play – One or more tasks executed on a given host(s)

Playbook – One or more plays. Each play can be executed on the same or different hosts

Role – Ansible roles allows you to group resources based on certain functionality/service such that they can be easily reused. In a role, you have directories for variables, defaults, files, templates, handlers, tasks, and metadata. You can then use the role by simply specifying it in your playbook.
```

* You want to run Ansible playbook only on specific minor version of your OS, how would you achieve that?

* Write a task to create the directory ‘/tmp/new_directory’

```
- name: Create a new directory
  file:
      path: "/tmp/new_directory"
      state: directory
```

* What would be the result of the following play?

```
---
- name: Print information about my host
  hosts: localhost
  gather_facts: 'no'                                                                                                                                                                           
  tasks:
      - name: Print hostname
        debug:
            msg: "It's me, {{ ansible_hostname }}"
```

```
When given a written code, always inspect it thoroughly. If your answer is “this will fail” then you are right. We are using a fact (ansible_hostname), which is a gathered piece of information from the host we are running on. But in this case, we disabled facts gathering (gather_facts: no) so the variable would be undefined which will result in failure.
```

* Write a playbook to install ‘zlib’ and ‘vim’ on all hosts if the file ‘/tmp/mario’ exists on the system.

```
---
- hosts: all
  vars:
      mario_file: /tmp/mario
      package_list:
          - 'zlib' 
          - 'vim'
  tasks:
      - name: Check for mario file
        stat:
            path: "{{ mario_file }}"
        register: mario_f

      - name: Install zlib and vim if mario file exists
        become: "yes"
        package:
            name: "{{ item }}"
            state: present
        with_items: "{{ package_list }}"
        when: mario_f.stat.exists
```

* Write a playbook to deploy the file ‘/tmp/system_info’ on all hosts except for controllers group, with the following content

  ```
  I'm <HOSTNAME> and my operating system is <OS>
  ```

  replace <HOSTNAME> and  <OS> with the actual data for the specific host you are running on

The playbook to deploy the system_info file

```
--- 
- name: Deploy /tmp/system_info file
  hosts: all:!controllers
  tasks: 
      - name: Deploy /tmp/system_info
        template:
            src: system_info.j2 
            dest: /tmp/system_info
```

The content of the system_info.j2 template

```
# {{ ansible_managed }}
I'm {{ ansible_hostname }} and my operating system is {{ ansible_distribution }
```

## Terraform

##### Beginner

* Can you explain what is Terraform? How it works?
* What benefits infrastructure-as-code has?

```
- fully automated process of provisoning, modifying and deleting your infrastructure
- version control for your infrastructure which allows you to quickly rollback to previous versions
- valide infrastructure quoality and stability with automated tests and code reviews
- makes infrastructure tasks less reptitive
```

* Why Terraform and not other technologies? (e.g. Ansible, Puppet, CloufFormation)


## Containers

* How containers different from VMs?
* In which scenarios would you use containers and in which you would prefer to use VMs?

## Docker

* What happens when you run `docker run hello-world`?

```
Docker CLI passes your request to Docker daemon.
Docker daemon downloads the image from Docker Hub
Docker daemon creates a new container by using the image it downloaded
Docker daemon redirects output from container to Docker CLI which redirects it to the standard output
```

* How do you run a container?

* What do you see when you run `docker ps`?

* What `docker commit` does? when will you use it?

* Explain what is Dockerfile used for and the content of the following Dockerfile

```
FROM registry.access.redhat.com/rhel7/rhel

RUN yum -y install httpd && yum -y update; yum clean all

EXPOSE 80
ENTRYPOINT [ "/usr/sbin/httpd" ]
CMD [ "-D", "FOREGROUND" ]
```

Answer:

```
Use the image 'rhel7/rhel' from the registry 'registry.access.redhat.com` to run httpd.
Befor running it, install the httpd package, update all packages and expose port 80.
```

* How would you transfer data from one container into another?

* What is the difference between ADD and COPY in Dockerfile?
* What is the difference between CMD and RUN in Dockerfile?

* Explain what is Docker compose and what is it used for
* What are the differences between Docker compose, Docker swarm and Kuberenets?

* Explain Docker interlock

* What is the difference between Docker Hub and Docker cloud?

```
Docker Hub is a native Docker registry service which allows you to run pull
and push commands to install and deploy Docker images from the Docker Hub.

Docker Cloud is built on top of the Docker Hub so Docker Cloud provides
you with more options/features compared to Docker Hub. One example is
Swarm management which means you can create new swarms in Docker Cloud.
```

## Kubernetes

* What is Kubernetes?
* Why Docker isn't enough? Why do we need Kubernetes?
* Describe the architecture of Kuberenets
* How do you monitor your Kuberenets?
* What is kubectl? How do you use it?
* What is kubconfig? What do you use it for?
* How do you create users?


## Python

##### beginner

* What data type supported in Python and which of them are mutable?
  What function can you use to show that a certain data type is mutable?

```
The mutable data types are:

    List
    Dictionary
    Set
    
The immutable data types are:

    Numbers (int, float, ...)
    String
    Bool
    Tuple

The id function can be used to check if a given variable is mutable or not.
```

* What is PEP8? Give an example of 5 style guidelines

```
PEP8 is a list of coding conventions and style guidelines for Python

5 style guidelines:

    1. Limit all lines to a maximum of 79 characters.
    2. Surround top-level function and class definitions with two blank lines.
    3. Use commas when making a tuple of one element
    4. Use spaces (and not tabs) for indentation
    5. Use 4 spaces per indentation level
```

* Write a program which will revert a string (e.g. pizza -> azzip)

```
Shortest way is str[::-1]

"Classic" way:
```

##### Intermediate

* What _ is used for in Python?

```
1. Translation lookup in i18n
2. Hold the result of the last executed expression or statement
3. As a general purpose "throwaway" variable name. For example: x, y, _ = get_data() (x and y are used but since we don't care about third variable, we "threw it away").
```

* Sort a list of lists by the second item of each nested list

```
li = [[1, 4], [2, 1], [3, 9], [4, 2], [4, 5]]

sorted(x, key=lambda l: l[1])
```

* You have the following lists: [{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}]
  Extract all type of foods. Final output should be: {'mushrooms', 'goombas', 'turtles'}

```
set([food for bro in x for food in bro['food']])
```

## Prometheus

* Describe the following Prometheus components:
  - Prometheus server
  - Push Gateway
  - Alert Manager

```
Prometheus server responsible for scraping the storing the data
Push gateway is used for short-lived jobs
Alert manager is responsible for alerts ;)
```

* What is an exporter? What is it used for?

## Git

###### beginner

<details>
<summary>What is the difference between `git pull` and `git fetch`?</summary>

Shortly, git pull = git fetch + git merge

When you run git pull, it gets all the changes from the remote or central
repository and attaches it to your corresponding branch in your local reposistory.

git fetch gets all the changes from the remote repository, stores the changes in
a separate branch in your local repository
</details>

<details>
<summary>Explain the following: `git directory`, `working directory` and `staging area`
</summary>

The Git directory is where Git stores the metadata and object database for your project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer.

The working directory is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify.

The staging area is a simple file, generally contained in your Git directory, that stores information about what will go into your next commit. It’s sometimes referred to as the index, but it’s becoming standard to refer to it as the staging area.

This answer taken from [git-scm.com](https://git-scm.com/book/en/v1/Getting-Started-Git-Basics#_the_three_states)
</details>
<details>
<summary>How do you resolve git conflicts?</summary>
</details>
<details>
<summary>What is the difference between `git reset` and `git reverse`?</summary>
</details>
<details>
<summary>In what situations are you using `git rebase`?</summary>
</details>
<details>
<summary>What branching strategies are you familiar with?</summary>
</details>
<details>
<summary>Explain octopus strategy</summary>
</details>

## Scenarios

Scenarios are questions which combine several subjects together. Some scenarios will
require from you to design, plan and implement environments with different constraints
and considerations.

* [Elasticsearch & Kibana on AWS](scenarios/elk_kibana_aws.md)
* [Ansible, Minikube and Docker](scenarios/ansible_minikube_docker.md)
