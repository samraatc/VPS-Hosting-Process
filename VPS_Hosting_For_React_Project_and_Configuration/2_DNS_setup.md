# DNS settings Requiments

1. Domain Name
2. DNS server IP address / vps IP address
3. DNS Records settings where records are stored to manage DNS

## How to Point Domain to particular IP Server or VPS

- Login to Your Domain Provider Website
- Navigate to Manage DNS
- Add Following Records:


| Type | Host/Name | Value                             |
| ----- | -----    | --------                          |
| A     | @        | Your Remote Server IP / VPS IP    |   
| A     | www      | Your Remote Server IP / VPS IP    |
| AAAA  | @        | Your Remote Server IPv6 / VPS IP  |
| AAAA  | www      | Your Remote Server IPv6  / VPS IP |

- after setting up the above DNS YOUR_DOMAIN will be pointing to the specified IP Server or VPS
