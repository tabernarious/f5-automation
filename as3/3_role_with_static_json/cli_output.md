


```
$ ansible-playbook post_at_declaration2.yml

PLAY [POST F5 ATC Declaration] **************************************************************************************

TASK [F5 ATC POST] **************************************************************************************************

TASK [f5devcentral.atc_deploy : Setup provider and varables] ********************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Get declaration from file] **********************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Download file if url specified] *****************************************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : Update the atc_declaration] *********************************************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : Set Automated Tool Chain service type from file] ************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Validate if atc_service name is correct if defined] *********************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : Set Automated Tool Chain metadata] **************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Setup service "AS3" endpoints] ******************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : include authentication.yaml] ********************************************************
included: /home/danielt/.ansible/roles/f5devcentral.atc_deploy/tasks/authentication.yaml for bigip102

TASK [f5devcentral.atc_deploy : Get authentication token] ***********************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Set the token fact if authentication succeeded] *************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Test authentication] ****************************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Verify "AS3" service is available, and collect service info] ************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : include as3_filtering.yaml] *********************************************************
included: /home/danielt/.ansible/roles/f5devcentral.atc_deploy/tasks/as3_filtering.yaml for bigip102

TASK [f5devcentral.atc_deploy : Setup AS3 endpoint with specified tenant when tenant specified] *********************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Setup URL query 'show' when using GET, POST, or DELETE with AS3] ********************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Setup optional URL query 'showHash' when using POST with AS3] ***********************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : Setup URL query 'async' when using POST with AS3] ***********************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : check as3 declaration and include teem data if needed] ******************************
changed: [bigip102]

TASK [f5devcentral.atc_deploy : Update the atc_declaration] *********************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : include declare.yaml] ***************************************************************
included: /home/danielt/.ansible/roles/f5devcentral.atc_deploy/tasks/declare.yaml for bigip102

TASK [f5devcentral.atc_deploy : POST AS3 declaration] ***************************************************************
ok: [bigip102]

TASK [f5devcentral.atc_deploy : POST DO declaration] ****************************************************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : POST TS declaration] ****************************************************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : GET AS3 declaration] ****************************************************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : Check if BIG-IQ (ignore if failed)] *************************************************
fatal: [bigip102]: FAILED! => {"accept_ranges": "bytes", "changed": false, "connection": "close", "content": "<?xml v                                                                                                                        ersion=\"1.0\" encoding=\"ISO-8859-1\"?>\n<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Strict//EN\"\n  \"http://www.                                                                                                                        w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd\">\n<html xmlns=\"http://www.w3.org/1999/xhtml\" lang=\"en\" xml:lang=\"en\">\                                                                                                                        n<head>\n<title>Object not found!</title>\n<link rev=\"made\" href=\"mailto:support@f5.com\" />\n<style type=\"text/c                                                                                                                        ss\"><!--/*--><![CDATA[/*><!--*/ \n    body { color: #000000; background-color: #FFFFFF; }\n    a:link { color: #0000                                                                                                                        CC; }\n    p, address {margin-left: 3em;}\n    span {font-size: smaller;}\n/*]]>*/--></style>\n<style type=\"text/css                                                                                                                        \"><!--/*--><![CDATA[/*><!--*/ \n* { width: 400px; font-size: 100%; font-style: normal; }\nhtml { text-align: center;                                                                                                                         }\nbody { background: #ffffff; text-align: left; font-family: sans-serif; font-size: 70%; color: #333333; }\n\na,spa                                                                                                                        n { width: auto; } \nh1,h2,h3 { margin: 20px 0px 20px 0px; font-weight: bold; }\n\nh1 { padding: 5px; border: 1px sol                                                                                                                        id #999999; background: #eeeeee; color: #000000; font-size: 125%;  }\nhr { height: 1px; border: none; border-top: 1px                                                                                                                         solid #999999; }\nimg { border: 0px; }\np { width: 350px; margin: 15px 25px 15px 25px; line-height: 135%; }\n/*]]>*/                                                                                                                        --></style>\n\n</head>\n\n<body>\n<h1>Object not found!</h1>\n<p>\n\n\n    The requested URL was not found on this se                                                                                                                        rver.\n\n    If you entered the URL manually please check your\n    spelling and try again.\n\n</p>\n\n<h2>Error 404<                                                                                                                        /h2>\n<address>\n  <a href=\"/\">10.10.102.1</a><br />\n  \n  <span>Thu Oct 29 17:56:28 2020<br />\n  </span>\n</addr                                                                                                                        ess>\n</body>\n</html>\n\n", "content_language": "en", "content_security_policy": "default-src 'self' https://sentine                                                                                                                        l.whitehatsec.com https://api.ctscloud.com https://key.ctscloud.com 'unsafe-inline' 'unsafe-eval' data: blob:; img-sr                                                                                                                        c 'self' data: https://sentinel.whitehatsec.com https://api.ctscloud.com https://key.ctscloud.com http://127.4.1.1 ht                                                                                                                        tp://127.4.2.1", "content_type": "text/html; charset=iso-8859-1", "date": "Thu, 29 Oct 2020 22:56:28 GMT", "elapsed":                                                                                                                         0, "msg": "Status code was 404 and not [200]: HTTP Error 404: Not Found", "redirected": false, "server": "Apache", "                                                                                                                        status": 404, "strict_transport_security": "max-age=16070400; includeSubDomains", "transfer_encoding": "chunked", "ur                                                                                                                        l": "https://10.10.102.1:443/info/system", "vary": "accept-language,accept-charset", "x_content_type_options": "nosni                                                                                                                        ff", "x_frame_options": "SAMEORIGIN", "x_xss_protection": "1; mode=block"}
...ignoring

TASK [f5devcentral.atc_deploy : include atc_task_check_bigip.yaml] **************************************************
included: /home/danielt/.ansible/roles/f5devcentral.atc_deploy/tasks/atc_task_check_bigip.yaml for bigip102

TASK [f5devcentral.atc_deploy : Wait for AS3 Task to complete] ******************************************************
FAILED - RETRYING: Wait for AS3 Task to complete (5 retries left).
ok: [bigip102]

TASK [f5devcentral.atc_deploy : Wait for DO Task to complete] *******************************************************
skipping: [bigip102]

TASK [f5devcentral.atc_deploy : include atc_task_check_bigiq.yaml] **************************************************
skipping: [bigip102]

TASK [debug] ********************************************************************************************************
ok: [bigip102] => {
    "atc_AS3_status": {
        "accept_encoding": "identity",
        "allow": "",
        "attempts": 2,
        "cache_control": "no-store, no-cache, must-revalidate",
        "changed": false,
        "connection": "close",
        "content": "{\"id\":\"8832199c-d448-473f-a532-fbead679d581\",\"results\":[{\"code\":200,\"message\":\"no chan                                                                                                                        ge\",\"host\":\"localhost\",\"tenant\":\"Sample_01\",\"runTime\":1207}],\"declaration\":{\"Sample_01\":{\"A1\":{\"web                                                                                                                        _pool\":{\"class\":\"Pool\",\"members\":[{\"serverAddresses\":[\"10.30.0.5\",\"192.0.1.11\"],\"servicePort\":80}],\"m                                                                                                                        onitors\":[\"http\"]},\"class\":\"Application\",\"template\":\"generic\",\"serviceBlah\":{\"class\":\"Service_HTTP\",                                                                                                                        \"pool\":\"web_pool\",\"virtualAddresses\":[\"10.20.102.160\"]}},\"class\":\"Tenant\"},\"remark\":\"Simple HTTP Servi                                                                                                                        ce with Round-Robin Load Balancing\",\"controls\":{\"userAgent\":\"ansible/2.9.13\",\"class\":\"Controls\",\"archiveT                                                                                                                        imestamp\":\"2020-10-29T22:56:29.703Z\"},\"label\":\"Sample 1\",\"id\":\"urn:uuid:ad80f547-94a7-4c22-9267-189564bc4e8                                                                                                                        e\",\"schemaVersion\":\"3.0.0\",\"class\":\"ADC\",\"updateMode\":\"selective\"}}",
        "content_length": "767",
        "content_security_policy": "default-src 'self' https://sentinel.whitehatsec.com https://api.ctscloud.com http                                                                                                                        s://key.ctscloud.com 'unsafe-inline' 'unsafe-eval' data: blob:; img-src 'self' data: https://sentinel.whitehatsec.com                                                                                                                         https://api.ctscloud.com https://key.ctscloud.com http://127.4.1.1 http://127.4.2.1",
        "content_type": "application/json",
        "cookies": {},
        "cookies_string": "",
        "date": "29 Oct 2020 22:56:39 UTC",
        "elapsed": 0,
        "expires": "-1",
        "failed": false,
        "failed_when_result": false,
        "json": {
            "declaration": {
                "Sample_01": {
                    "A1": {
                        "class": "Application",
                        "serviceBlah": {
                            "class": "Service_HTTP",
                            "pool": "web_pool",
                            "virtualAddresses": [
                                "10.20.102.160"
                            ]
                        },
                        "template": "generic",
                        "web_pool": {
                            "class": "Pool",
                            "members": [
                                {
                                    "serverAddresses": [
                                        "10.30.0.5",
                                        "192.0.1.11"
                                    ],
                                    "servicePort": 80
                                }
                            ],
                            "monitors": [
                                "http"
                            ]
                        }
                    },
                    "class": "Tenant"
                },
                "class": "ADC",
                "controls": {
                    "archiveTimestamp": "2020-10-29T22:56:29.703Z",
                    "class": "Controls",
                    "userAgent": "ansible/2.9.13"
                },
                "id": "urn:uuid:ad80f547-94a7-4c22-9267-189564bc4e8e",
                "label": "Sample 1",
                "remark": "Simple HTTP Service with Round-Robin Load Balancing",
                "schemaVersion": "3.0.0",
                "updateMode": "selective"
            },
            "id": "8832199c-d448-473f-a532-fbead679d581",
            "results": [
                {
                    "code": 200,
                    "host": "localhost",
                    "message": "no change",
                    "runTime": 1207,
                    "tenant": "Sample_01"
                }
            ]
        },
        "local_ip_from_httpd": "10.10.102.1",
        "msg": "OK (767 bytes)",
        "pragma": "no-cache",
        "redirected": false,
        "server": "com.f5.rest.common.RestRequestSender",
        "status": 200,
        "strict_transport_security": "max-age=16070400; includeSubDomains",
        "url": "https://10.10.102.1:443/mgmt/shared/appsvcs/task/8832199c-d448-473f-a532-fbead679d581",
        "x_content_type_options": "nosniff",
        "x_f5_new_authtok_reqd": "false",
        "x_forwarded_host": "10.10.102.1:443",
        "x_forwarded_proto": "http",
        "x_forwarded_server": "localhost.localdomain",
        "x_frame_options": "SAMEORIGIN",
        "x_xss_protection": "1; mode=block"
    }
}

PLAY RECAP **********************************************************************************************************
bigip102                   : ok=22   changed=1    unreachable=0    failed=0    skipped=9    rescued=0    ignored=1
```