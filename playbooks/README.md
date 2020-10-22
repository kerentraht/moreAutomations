## Create new Account Usage
Below are instructions for using the `create_account.yml` playbook.

the `create_account.yml` playbook automates the creation of a new tenancy account in Cloud Central. 
The user running the playbook will be automatically assigned as the admin of the newly created account.

### Usage

Run the following command from the main folder of this repository with extre-vars as explained below (do not keep the square brackets in the final command).:

```
ansible-playbook playnooks/create_account.yml --extra-vars="refresh_token=[YOUR_REFRESH_TOKEN] account_name=[NEW_ACCOUNT_NAME]"
```
- refreash_token: Your refresh token for all Cloud Central APIs (more information in the main repo)
- account_name: The desired name for the new account

#### Example: 
```
ansible-playbook playbooks/crerate_account_2.yml --extra-vars="refresh_token=BDYdfec4REFh74uhend9H89-h9ksjdf423 account_name=my_new_account
```

#### Example success result:

```ShellSession
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'

PLAY [Create new account] ***********************************************************************************************************

TASK [Get API Token] ****************************************************************************************************************
ok: [localhost]

TASK [set bearer token & token_type] ************************************************************************************************
ok: [localhost]

TASK [set_fact] *********************************************************************************************************************
ok: [localhost]

TASK [Get Account] ******************************************************************************************************************
ok: [localhost]

TASK [set_fact] *********************************************************************************************************************
ok: [localhost]

TASK [extract accounts names] *******************************************************************************************************
ok: [localhost]

TASK [Print axisting accounts] ******************************************************************************************************
ok: [localhost] => {
    "msg": [
        "Default",
        "Demo",
        "Netapp",
        "testAccount",
    ]
}

TASK [Send create API request] ******************************************************************************************************
ok: [localhost]

TASK [set_fact] *********************************************************************************************************************
ok: [localhost]

TASK [Print result] *****************************************************************************************************************
ok: [localhost] => {
    "msg": "An account named : Tests5 was successfully created. New account ID is: account-NLtsKvm"
}

TASK [Print Errors] *****************************************************************************************************************
skipping: [localhost]

PLAY RECAP **************************************************************************************************************************
localhost                  : ok=10   changed=0    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0  
```


