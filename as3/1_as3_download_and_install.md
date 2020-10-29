# AS3 Download and Install (Using cURL)

* https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/userguide/installation.html
* https://github.com/F5Networks/f5-appsvcs-extension
* https://github.com/F5Networks/f5-appsvcs-extension/releases

### Download
```
$ curl -L https://github.com/F5Networks/f5-appsvcs-extension/releases/download/v3.23.0/f5-appsvcs-3.23.0-5.noarch.rpm.sha256 > /var/config/rest/downloads/f5-appsvcs-3.23.0-5.noarch.rpm.sha256

$ curl -L https://github.com/F5Networks/f5-appsvcs-extension/releases/download/v3.23.0/f5-appsvcs-3.23.0-5.noarch.rpm > /var/config/rest/downloads/f5-appsvcs-3.23.0-5.noarch.rpm

$ sha256sum /var/config/rest/downloads/f5-appsvcs-3.23.0-5.noarch.rpm.sha256 --check
```

### Enable iApps > Package Management LX (prior to v14.0)
```
## For BIG-IP versions prior to 14.0 you must run this command to install AS3 from the GUI (enables GUI > iApps > Package Management LX). After running this command reload the GUI page and open the iApps menu.
$ touch /var/config/rest/iapps/enable
```

### Set Variables
```
$ FN=f5-appsvcs-3.23.0-5.noarch.rpm

## This MUST be admin user!
$ CREDS=admin:admin

$ IP=10.10.102.1

$ DATA="{\"operation\":\"INSTALL\",\"packageFilePath\":\"/var/config/rest/downloads/$FN\"}"
```

### Install AS3 RPM (can be done from BIG-IP CLI logged in as root user)
```
$ curl -kvu $CREDS "https://$IP/mgmt/shared/iapp/package-management-tasks" -H "Origin: https://$IP" -H 'Content-Type: application/json;charset=UTF-8' --data $DATA
```
### AS3 Installation Output (raw)
```
*   Trying 10.10.102.1...
* Connected to 10.10.102.1 (10.10.102.1) port 443 (#0)
* Cipher selection: ALL:!EXPORT:!EXPORT40:!EXPORT56:!aNULL:!LOW:!RC4:@STRENGTH
* successfully set certificate verify locations:
*   CAfile: /etc/pki/tls/certs/ca-bundle.crt
  CApath: none
* TLSv1.2 (OUT), TLS handshake, Client hello (1):
* TLSv1.2 (IN), TLS handshake, Server hello (2):
* TLSv1.2 (IN), TLS handshake, Certificate (11):
* TLSv1.2 (IN), TLS handshake, Server key exchange (12):
* TLSv1.2 (IN), TLS handshake, Server finished (14):
* TLSv1.2 (OUT), TLS handshake, Client key exchange (16):
* TLSv1.2 (OUT), TLS change cipher, Client hello (1):
* TLSv1.2 (OUT), TLS handshake, Finished (20):
* TLSv1.2 (IN), TLS change cipher, Client hello (1):
* TLSv1.2 (IN), TLS handshake, Finished (20):
* SSL connection using TLSv1.2 / ECDHE-RSA-AES128-GCM-SHA256
* Server certificate:
*        subject: C=US; ST=WA; L=Seattle; O=MyCompany; OU=MyOrg; CN=bigip102.tabernarious.net; emailAddress=root@localhost.localdomain
*        start date: Aug 21 04:58:30 2020 GMT
*        expire date: Aug 21 04:58:30 2021 GMT
*        issuer: C=US; ST=WA; L=Seattle; O=MyCompany; OU=MyOrg; CN=bigip102.tabernarious.net; emailAddress=root@localhost.localdomain
*        SSL certificate verify result: self signed certificate (18), continuing anyway.
* Server auth using Basic with user 'admin'
> POST /mgmt/shared/iapp/package-management-tasks HTTP/1.1
> Host: 10.10.102.1
> Authorization: Basic YWRtaW46YWRtaW4=
> User-Agent: curl/7.47.1
> Accept: */*
> Origin: https://10.10.102.1
> Content-Type: application/json;charset=UTF-8
> Content-Length: 101
>
* upload completely sent off: 101 out of 101 bytes
< HTTP/1.1 202 Accepted
< Date: 29 Oct 2020 03:10:29 UTC
< Server: com.f5.rest.common.RestRequestSender
< Set-Cookie: BIGIPAuthCookie=2EA0346A178B6BE50430C477A93B53D0788E4C1D; path=/; Secure; HttpOnly
< Set-Cookie: BIGIPAuthUsernameCookie=admin; path=/; Secure; HttpOnly
< X-Frame-Options: SAMEORIGIN
< Strict-Transport-Security: max-age=16070400; includeSubDomains
< Pragma: no-cache
< Cache-Control: no-store, no-cache, must-revalidate
< Expires: -1
< Content-Length: 615
< Content-Type: application/json
< REMOTEROLE: 0
< Local-Ip-From-Httpd: 10.10.102.1
< Session-Invalid: true
< X-Forwarded-Server: localhost.localdomain
< X-Forwarded-Proto: http
< Origin: https://10.10.102.1
< X-F5-New-Authtok-Reqd: false
< REMOTECONSOLE: /sbin/nologin
< X-Forwarded-Host: 10.10.102.1
< X-Content-Type-Options: nosniff
< X-XSS-Protection: 1; mode=block
< Content-Security-Policy: default-src 'self' https://sentinel.whitehatsec.com https://api.ctscloud.com https://key.ctscloud.com 'unsafe-inline' 'unsafe-eval' data: blob:; img-src 'self' data: https://sentinel.whitehatsec.com https://api.ctscloud.com https://key.ctscloud.com http://127.4.1.1 http://127.4.2.1
<
* Connection #0 to host 10.10.102.1 left intact
{"packageFilePath":"/var/config/rest/downloads/f5-appsvcs-3.23.0-5.noarch.rpm","operation":"INSTALL","id":"51a7efd0-7314-41aa-a16c-1c4ae151a43e","status":"CREATED","userReference":{"link":"https://localhost/mgmt/shared/authz/users/admin"},"identityReferences":[{"link":"https://localhost/mgmt/shared/authz/users/admin"}],"ownerMachineId":"98a87ae5-194e-48f6-b238-9a85e9ad73ca","generation":1,"lastUpdateMicros":1603941029832004,"kind":"shared:iapp:package-management-tasks:iapppackagemanagementtaskstate","selfLink":"https://localhost/mgmt/shared/iapp/package-management-tasks/51a7efd0-7314-41aa-a16c-1c4ae151a43e"}
```

### AS3 Installation Result (pretty json)
```json
{
  "packageFilePath": "/var/config/rest/downloads/f5-appsvcs-3.23.0-5.noarch.rpm",
  "operation": "INSTALL",
  "id": "51a7efd0-7314-41aa-a16c-1c4ae151a43e",
  "status": "CREATED",
  "userReference": {
    "link": "https://localhost/mgmt/shared/authz/users/admin"
  },
  "identityReferences": [
    {
      "link": "https://localhost/mgmt/shared/authz/users/admin"
    }
  ],
  "ownerMachineId": "98a87ae5-194e-48f6-b238-9a85e9ad73ca",
  "generation": 1,
  "lastUpdateMicros": 1603941029832004,
  "kind": "shared:iapp:package-management-tasks:iapppackagemanagementtaskstate",
  "selfLink": "https://localhost/mgmt/shared/iapp/package-management-tasks/51a7efd0-7314-41aa-a16c-1c4ae151a43e"
}
```

### cURL for AS3 Status
```
$ curl -kvu $CREDS "https://$IP/mgmt/shared/appsvcs/info"
```
```json
{"version":"3.23.0","release":"5","schemaCurrent":"3.23.0","schemaMinimum":"3.0.0"}
```
```json
{
  "version": "3.23.0",
  "release": "5",
  "schemaCurrent": "3.23.0",
  "schemaMinimum": "3.0.0"
}
```