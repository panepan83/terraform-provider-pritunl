---
page_title: "pritunl_user Resource - terraform-provider-pritunl"
subcategory: ""
description: |-
  The organization resource allows managing information about a particular Pritunl user.
---

# Resource `pritunl_user`

## Schema

### Required

- **name** (String) The name of the user.
- **organization_id** (String) The organizations that user belongs to.

### Optional

- **auth_type** (String) User authentication type. This will determine how the user authenticates. This should be set automatically when the user authenticates with single sign-on.
- **bypass_secondary** (Boolean) Bypass secondary authentication such as the PIN and two-factor authentication. Use for server users that can't provide a two-factor code.
- **client_to_client** (Boolean) Only allow this client to communicate with other clients. Access to routed networks will be blocked.
- **disabled** (Boolean) Shows if user is disabled
- **dns_servers** (List of String) Dns server with port to forward sub-domain dns requests coming from this users domain. Multiple dns servers may be separated by a comma.
- **dns_suffix** (String) The suffix to use when forwarding dns requests. The full dns request will be the combination of the sub-domain of the users dns name suffixed by the dns suffix.
- **email** (String) User email address.
- **groups** (List of String) Enter list of groups to allow connections from. Names are case sensitive. If empty all groups will able to connect.
- **id** (String) The ID of this resource.
- **mac_addresses** (List of String) Comma separated list of MAC addresses client is allowed to connect from. The validity of the MAC address provided by the VPN client cannot be verified.
- **network_links** (List of String) Network address with cidr subnet. This will provision access to a clients local network to the attached vpn servers and other clients. Multiple networks may be separated by a comma. Router must have a static route to VPN virtual network through client.
- **port_forwarding** (List of Map of String) Comma seperated list of ports to forward using format source_port:dest_port/protocol or start_port-end_port/protocol. Such as 80, 80/tcp, 80:8000/tcp, 1000-2000/udp.

