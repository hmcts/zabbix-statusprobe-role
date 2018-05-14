zabbix-statusprobe-role
=========

Generally phased out, retained for historic reasons.

Role to install the application status probe on host. Depends on zabbixagent-role.

Role Variables
--------------
You need to provide the app name ("app"), type of check ("type" - of a value equal to either "health" or "metrics") and URI of the endpoint ("uri") for every check exposed by your app.

For tactical, this is most likely a single URL to check the status of the app (returning a JSON object with a top level field of "status" with value of "UP" or "DOWN"). All other fields are sent but ignored by Zabbix server at the moment.

```yaml
zabbix_probe_checks:
  - {app: "default", type: "health", uri: "http://localhost/status/health"}
```

License
-------
MIT

Author Information
------------------
HMCTS Reform Programme
