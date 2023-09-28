# Nutanix Role for Prism DNS server configuration

This Ansible role sets the DNS server configuration for Prism Element and Prism Central.


## Role Variables

| Variable                              | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|---------------------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| role_nutanix_prism_dns_host           | yes      |         |                                                                                 | The IP address or FQDN for the Prism (Element or Central) to which you want to connect.                                                            |
| role_nutanix_prism_dns_username       | yes      |         |                                                                                 | A valid username with appropriate rights to access the Nutanix API.                                                                                |
| role_nutanix_prism_dns_password       | yes      |         |                                                                                 | A valid password for the supplied username.                                                                                                        |
| role_nutanix_prism_dns_port           | no       | 9440    |                                                                                 | The Prism TCP port.                                                                                                                                |
| role_nutanix_prism_dns_validate_certs | no       | false   | true / false                                                                    | Whether to check if Prism UI certificates are valid.                                                                                               |
| role_nutanix_prism_dns_debug          | no       | false   | true / false                                                                    | Debuging output.                                                                                                                                   |
| role_nutanix_prism_dns_list           | yes      | []      |                                                                                 | Provide a list of DNS server IP addresses; ["8.8.8.8", "8.8.4.4"].                                                                                 |

## Dependencies

- grdavies.role_nutanix_prism_api

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - role: grdavies.role_nutanix_prism_dns
  vars:
    role_nutanix_prism_dns_host: 10.38.185.37
    role_nutanix_prism_dns_password: admin
    role_nutanix_prism_dns_username: nx2Tech165!
    role_nutanix_prism_dns_list:
      - 8.8.8.8
      - 8.8.4.4
```

## License

See LICENSE.md

## Author Information

Ross Davies
