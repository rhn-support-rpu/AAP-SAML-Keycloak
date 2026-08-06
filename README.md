# AAP-SAML-Keycloak


# 1. setup keycloak on target node (become true)
~~~
$ ansible-playbook -i <inventory> keycloak_setup.yml -K
~~~

# 2. configure SAML authentication method on AAP (become false)
~~~
$ ansible-playbook -i <inventory> aap_saml_config.yml
~~~
