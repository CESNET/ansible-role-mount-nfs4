cesnet.mount_nfs4
======================

Ansible Galaxy role [cesnet.mount_nfs4](https://galaxy.ansible.com/cesnet/mount_nfs4) 
that installs a NFSv4 client and mounts remote filesystems into local directories.

Use "--tags config" to run only config.

Requirements
------------

You must provide a Kerberos keytab file (usually encrypted by ansible-vault) in file files/krb5.keytab
or in other file with its name defined in the variable krb5_keytab_file.

Role Variables
--------------
- krb5_conf_file - name of file with Kerberos config, default is krb5.conf, default file is provided
- krb5_keytab_file - name of with Kerberos keytab, default is krb5.keytab
- mount_nfs4_mounts - list of filesystems to mount

Example Playbook
----------------
```yaml
- hosts: all
  roles:
    - role: cesnet.mount_nfs4l
      vars:
        mount_nfs4_mounts:
          - { path: '/storage/brno1-cerit', src: 'storage-brno1-cerit.metacentrum.cz:/hsmcerit' }
          - { path: '/storage/brno3-cerit', src: 'storage-brno3-cerit.metacentrum.cz:/' }
```
