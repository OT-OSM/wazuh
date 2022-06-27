## Ansible Role: Wazuh-Manager

Ansible role to setup, manage Wazuh -Manager standalone

Some of the highlighting features are:-

  - Standalone setup of Wazuh-manager
  - Setup Slack for alert management
 

### Supported OS
- Ubuntu 18 
- Ubuntu 20
- Ubuntu 22

### Requirements

**No third party requirement is needed by this role**

### Roles Variables

Roles variables are categorized into two divisions i.e. Mandatory and Optional.

#### Mandatory Variables

|**Variables**|**Default Values**|**Possible Values**|**Type**|**Description**|
|-------------|------------------|-------------------|--------|---------------|
| UbuntuVersion | 20.04 |<ul><li>18.04</li><li>20.04</li><li>22.04</li></ul>  | string | Operating system name and version |


#### Optional Variables

|**Variables**|**Default Values**|**Possible Values**|**Type**|**Description**|
|-------------|------------------|-------------------|--------|---------------|
| WazuhVersion | 4.3.0 | *Wazuh Version* | string | Default Version of wazuh |
| Slack | false | <ul><li>true</li><li>false</li></ul> | boolean | To configure Slack in our wazuh manager |
| SlackWebhook | None | webhook String | String | Mandatory value if Slack Variable value is true |


### Usage

The inventory for wazuh_manager role should look like this:-

```ini
[wazuh]
node-1 ansible_host=13.213.39.180

[wazuh:vars]
ansible_ssh_user=ubuntu
```


An example playbook should look like this:-

```yaml
---
- name: wazuh
  hosts: all
  become_user: root
  roles:
   - { role: wazuh }
```

and for running the ansible role, we will use ansible cli.

```shell
ansible-playbook -i tests/inventory tests/test.yml
```
## Authors

**[Varghese Kurian](varghese.palamoottil@opstree.com)**
