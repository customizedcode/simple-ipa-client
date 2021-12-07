simple-ipa-client
=========

Ansible role to install ipa client with simple options  

Since this role is unattended install, you need to create the bulk passwords
for this role when it executes.

<pre>
$ kinit admin
$ ipa host-add "hostname-fqdn" --ip-address=a.b.c.d --password=enrollpass --force # if host/dns ip address is not setup.
$ ipa host-add "hostname-fqdn" --password=enrollpass --force # if host/dns ip address is setup in ipa
</pre>

Example Playbook
----------------
<pre>

hosts: ipaclients  
become: yes  

  roles:  
    - role: simple-ipa-client  
        var:  
          enroll_pass_var: 'password'  
          enroll_password_var: 'enrollpass'
          domain_var: 'customized.local'
          realm_var: 'CUSTOMIZED.LOCAL'
          ipa_server_fqdn_var: 'ipa.customized.local'

</pre>  

License
-------

MIT

Author Information
------------------
Roy Kim  
https://github.com/customizedcode  
customizedcode.us  