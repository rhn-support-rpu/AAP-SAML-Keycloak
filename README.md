# AAP-SAML-Keycloak
This will create SAML base on the Keycloak, and configure the SAML authentication method in AAP.
- Keycload access URL will be http://{{keycloak_hostname}}:8080
- It will create an aap realm with a testuser
- Keycload admin and testuser password will be what you set in the inventory
- Optional: deploy ldap server (OpenLDAP) on port 3890

# Steps to deploy.
1. Edit inventory file

2. setup keycloak on target node (become true)
~~~
$ ansible-playbook -i <inventory> keycloak_setup.yml -K
~~~

3. configure SAML authentication method on AAP (become false)
~~~
$ ansible-playbook -i <inventory> aap_saml_config.yml
~~~

4. Optional: deploy ldap server with testuser1, testgroup1
~~~
$ ansible-playbook -i <inventory> LDAP_setup.yml
~~~
