# moreAutomations

This repo contains an Ansible-based automation for CVO customers, that retreives all resources of a user per account.

## Documentation
### Prerequesits:
- A server/computer that has https access to the internet (in particular to: **cloudmanager.netapp.com** and **cloudsync.netapp.com** )
- A valid version of Ansible installed
- The current dir cloned into the server
- An API refresh_token ([Click here](https://services.cloud.netapp.com/refresh-token) for the refresh token generator site)

### Usage

Run the following command from the main folder of this repository:
```
Ansible-playbook playbooks/get_working_environments.yml  --extra-vars="refresh_token=[YOUR_REFRESH_TOKEN]"
```

Example:

```
Ansible-playbook playbooks/get_working_environments.yml  --extra-vars="refresh_token=fdkjn3094uwer9u4rhedoif390e8whdf"
```

#### GOOD LUCK :+1:
