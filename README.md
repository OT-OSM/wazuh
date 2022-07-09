## Ansible Role: Wazuh-Manager

Ansible role to configure wazuh manager standalone with slack integration

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

#### Optional Variables

|**Variables**|**Default Values**|**Possible Values**|**Type**|**Description**|
|-------------|------------------|-------------------|--------|---------------|
| WazuhVersion | 4.3.0 | Wazuh Version | string | Default Version of wazuh |
| EnableSlack | false | <ul><li>true</li><li>false</li></ul> | boolean | To configure Slack in our wazuh manager |
| SlackWebhook | None | Webhook String | String | Mandatory value if Slack Variable value is true |
| ESPort | 9200 | Elasticsearch port | String | Default port of elasticsearch |
| CertificateScriptPath | /opt/ | PWD | String | Path were to load certificates |


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
   - { role: wazuh_manager }
```

and for running the ansible role, we will use ansible cli.

```shell
ansible-playbook -i tests/inventory tests/test.yml
```
## Authors

**[Varghese Kurian](varghese.palamoottil@opstree.com)**
