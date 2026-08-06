# AAP-SAML-Keycloak
This will create SAML base on the Keycloak, and configure the SAML authentication method in AAP.
- Keycload access URL will be http://{{keycloak_hostname}}:8080
- It will create an aap realm with a testuser
- Keycload admin and testuser password will be what you set in the inventory

Steps to deploy.
# 1. Edit inventory file eg. keycloak-inv.ini

# 2. setup keycloak on target node (become true)
~~~
$ ansible-playbook -i <inventory> keycloak_setup.yml -K
~~~

# 3. configure SAML authentication method on AAP (become false)
~~~
$ ansible-playbook -i <inventory> aap_saml_config.yml
~~~

