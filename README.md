# Introduction

How to use Nessus Professional API. (Ver.6)

# API

## Login Credential

POST id/password to `https://{IPADDR}:8834/session`. `-k` is "Don't verify certificate".

```
$ curl -k -X POST -H "Content-Type: application/json" -d @login.json https://192.168.2.80:8834/session
{"token":"5aea9270e4d576131696508c8efca505c32731d2881af43a"}
```

"token" is session id. You use this token as credential code.

## Scan

You can create scan template with API, but using WebGUI is easy way. In WebGUI, you can get scan number from URI.

```
$ curl -k -X POST -H "X-Cookie: token=5aea9270e4d576131696508c8efca505c32731d2881af43a" -d '' https://192.168.2.80:8834/scans/46/launch
$ {"scan_uuid":"f4d9d482-595d-78c2-a4c9-0236abc17804cfb1a36e863d7635"}
```

When you can get scan_uuid, scan is launched!

