# Nutanix Role for Prism DNS server configuration

This Ansible role sets the DNS server configuration for Prism Element and Prism Central.


## Role Variables

| Variable                 | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|--------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| nutanix_host             | yes      |         |                                                                                 | The IP address or FQDN for the Prism (Element or Central) to which you want to connect.                                                            |
| nutanix_username         | yes      |         |                                                                                 | A valid username with appropriate rights to access the Nutanix API.                                                                                |
| nutanix_password         | yes      |         |                                                                                 | A valid password for the supplied username.                                                                                                        |
| nutanix_port             | no       | 9440    |                                                                                 | The Prism TCP port.                                                                                                                                |
| validate_certs           | no       | no      | yes / no                                                                        | Whether to check if Prism UI certificates are valid.                                                                                               |
| nutanix_dns_server_list  | yes      | []      |                                                                                 | Provide a list of DNS server IP addresses; ["8.8.8.8", "8.8.4.4"].                                                                                 |

## Dependencies

NA

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - role: grdavies.role_nutanix_prism_dns
  vars:
    nutanix_host: 10.38.185.37
    nutanix_password: admin
    nutanix_username: nx2Tech165!
    nutanix_dns_server_list:
      - 8.8.8.8
      - 8.8.4.4
```

## License

See LICENSE.md

## Author Information

Ross Davies
