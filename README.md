Ansible Role: Configure SSH authentication for user's public key stored in AD
=========

Configure SSH authentication for user's public key stored in AD.

Requirements
------------

* The system is configured to connect directly to AD using SSSD.

* For the SSSD configuration, see [Connecting RHEL systems directly to AD using SSSD](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/integrating_rhel_systems_directly_with_windows_active_directory/connecting-rhel-systems-directly-to-ad-using-sssd_integrating-rhel-systems-directly-with-active-directory).

* For store ssh public key in AD, see [Store User SSH Keys in Active Directory for SSH Authentication](https://access.redhat.com/solutions/5353351)

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
ad_domain_name: "my.domain.com"
```

Set these variables in host_vars/hostname.yml to overwrite the default value.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers

  tasks:
    - name: config ssh authentication for user's public key stored in AD
      include_role:
        name: sfitpro.ssh_key_in_ad
        apply:
          tags:
            - ssh
      tags:
        - ssh
```

License
-------

BSD

Author Information
------------------

This role was created by Eddie Lu.
