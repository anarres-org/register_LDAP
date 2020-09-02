# Register LDAP

An [ansible](https://github.com/ansible) playbook to register a user in an LDAP
server.

## Compatibility

These are the tested GNU/Linux distributions. Probably it works with any
distribution.

* [debian](https://www.debian.org/)
  * buster

## Requirements

* `python`
* `ldap-utils`

## Role Variables

* `user_name`: Name of the user (eg. `John`).
* `surname`: Surname of the user (eg. `Doe`).
* `full_name`: Name and surname of the user (eg. `John Doe`).
* `nick`: Nickname of the user.
* `password`: Password for the user.
* `email`: Email account of the user.
* `gid`: Linux group ID for the user.
* `server_uri`: LDAP server uri (eg. `ldaps://anarres.local:636`).
* `validate_certs`: (Default: `true`) Boolean value for validating or not the
   LDAP server's certificates.
* `users_base_DN`: Base DN of the LDAP server where the user will be created (eg.
  `ou=users,dc=anarres,dc=local`).
* `bind_DN`: Bind DN to use to login to the LDAP server (eg.
  `cn=admin,dc=anarres,dc=local`).
* `bind_credentials`: Password for that account.
* `home_directory`: Path of the home directory of the new user (eg.
  `/home/users/john`).
* `get_highest_uid_command`: Shell command to get the highest uidNumber from
  the already registered user in the LDAP server.

## Dependencies

None.

## Testing

To test the project you need [molecule](http://molecule.readthedocs.io/en/latest/)
.

The testing dependencies are included as submoudules in
*molecule/dafault/roles/*. To fetch them automatically when cloning, use:

```bash
git clone --recurse-submodules -j10 [repo]
```

```bash
molecule test
```

## License

GPLv3

## Author Information

* **m0wer**: m0wer (at) autistici (dot) org
