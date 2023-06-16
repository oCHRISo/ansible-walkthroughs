# NGINX OSS, NGINX Agent and NGINX Management Suite

# Walkthrough Outcome

# Walkthrough steps

## NGINX Management Suite Certificate Files
Installing NMS requires the NMS certificate files to access the repository. Log in to [MyF5](https://account.f5.com/myf5) or follow the link in the trial activation email to download the NMS repo **.crt** and **.key** files:

* nginx-mgmt-suite-trial.key
* nginx-mgmt-suite-trial.crt

**NOTE:** Be sure to rename these files to `nginx-repo.key` and `nginx-repo.crt`, respectively.

## Installing NGINX Management Suite Role and Dependencies using Ansible Galaxy

1. Run `ansible-galaxy install -r requirements.yml` to install this role along with the required collections. If you already have these installed but need to update to newer versions, use `ansible-galaxy install -fr requirements.yml`.

## Execute install

1. Go to the inventory file and update hostname/ip address and username
```
[controlplane]
<hostname or ip address here> ansible_connection=ssh ansible_user=your-username-here

[dataplane]
<hostname or ip address here> ansible_connection=ssh ansible_user=your-username-here
```

2. Execute site.yml playbook
```
ansible-playbook -i inventory site.yml -vv
```