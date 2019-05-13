# Anstall
Anstall is an automated software installation tool for computer classrooms configuration and installation at Department of Computers and Informacits of Technical university of Košice. This project includes examples of usage for Windows based nodes management.

## Project Background
This project is part of the scientific [paper](https://madeja.github.io/publications/19-oss-conf-anstall.pdf) presented at [OSS Conf 2019](http://ossconf.soit.sk/).

## Used technologies
[Ansible](https://www.ansible.com/) is used as the main technology. To install ansible follow [Installation Giude](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

To setup Windows-based nodes see [How to set up a Windows Host](https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html).

## Usage

General manipulation:
```
# ping hosts
ansible-playbook playbooks/b512.yml --tags "ping"

# send msg to user
ansible-playbook playbooks/b512.yml --tags "msg-dontturnoff"

# shutdown or reboot
ansible-playbook playbooks/b512.yml --tags "shutdown"
ansible-playbook playbooks/b512.yml --tags "reboot"
```

Base packages install:
```
# run all tasks of base-pkg playbooks
ansible-playbook playbooks/b512.yml --tags "base-pkg"
```

Windows updates:
```
# enable win update service
ansible-playbook playbooks/b512.yml --tags "enable-win-update"	
# disable win update service
ansible-playbook playbooks/b512.yml --tags "disable-win-update"
# enable win update service, run updates and disable service
ansible-playbook playbooks/b512.yml --tags "run-win-updates"
```

Exam restrictions
```
# block internet for exam
ansible-playbook playbooks/b512.yml --tags "prog-block"
# unblock internet after exam
ansible-playbook playbooks/b512.yml --tags "prog-unblock"
```

Student account cleanup
```
# empty Downloads, Documents, Pictures and refresh Desktop
ansible-playbook playbooks/b512.yml --tags "cleanup"
```

Some virtualbox staff (hackaton 2017)
```
ansible-playbook playbooks/b512.yml --tags "hackaton-2017"
```

## Acknowledgment
This work was supported by project KEGA No. 053TU-KE-4/2019: Learning Software Engineering via Continues Challenges and Competitions.