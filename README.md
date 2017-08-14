# ldap
This repository will holds some useful example ldif's and command for ldap usage

## Commands
##### Find all users in ldap in the passed OU and DC only with their DN
```
ldapsearch -x -b "ou=People,dc=example,dc=com" -LLL uid | sed -n 's/^dn: // p' | grep uid
```
example output:
```
ldapsearch -x -b "ou=People,dc=example,dc=com" -LLL uid | sed -n 's/^dn: // p' | grep uid
```

##### Find all users in ldap in the passed OU and DC only with their DN and delete them
```
ldapsearch -x -b "ou=People,dc=example,dc=com" -LLL uid | sed -n 's/^dn: // p' | grep uid | ldapdelete -D "cn=admin,dc=example,dc=com" -w <password>
```
