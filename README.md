ansible-role-saprouter-deployment
===

```yml
- name: Ensure SAProuter instance is deployed
  vars:
    saprouter_deployment_bundle_local_dir: files/saprouter_deployment_bundle
    saprouter_deployment_bundle_saprouter_sar_file: saprouter_1011-80003478.sar
    saprouter_deployment_bundle_sapcryptolib_sar_file: SAPCRYPTOLIBP_8544-20011697.SAR
    saprouter_deployment_bundle_sapcar_file: SAPCAR_1115-70006178.EXE
  import_role:
    name: "mprusov.saprouter_deployment"
```

Location of original archives for SAProuter deployment
---

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_deployment_bundle_local_dir | The folder on ansible controller | files/saprouter_deployment_bundle |
| saprouter_deployment_bundle_remote_dir | The folder on the host | |
| saprouter_deployment_bundle_saprouter_sar_file | SAProuter SAR archive | saprouter_1011-80003478.sar |
| saprouter_deployment_bundle_sapcryptolib_sar_file | SAP Cryptolib SAR archive | SAPCRYPTOLIBP_8544-20011697.SAR |

Variables `saprouter_deployment_bundle_local_dir` and `saprouter_deployment_bundle_remote_dir` are mutually exclusive.

SAProuter's instance deployment parameters
---

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_deployment_sid | SID of SAProuter instance | R99 |
| saprouter_deployment_instance_number | Number of SAProuter instance  | '99' |
| saprouter_deployment_instance_name | SAProuter's instance name | "R{{ saprouter_deployment_instance_number }}" |
| saprouter_deployment_user_name | SAProuter administrator OS user | "{{ saprouter_deployment_sid \| lower }}adm" |
| saprouter_deployment_user_shell | Shell of the SAProuter owner | /bin/bash |
| saprouter_deployment_user_uid | User id of SAProuter owner | |
| saprouter_deployment_group_sapsys_gid | Group id of OS grpup sapsys | |
| saprouter_deployment_src_dir | | "/usr/sap/src/{{ saprouter_deployment_sid }}" |
| saprouter_regenerate_saprouttab_enabled | | false |

SAProuter start/stop script templates
---

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_start_script_template | | startsaprouter.sh.j2 |
| saprouter_stop_script_template | | stopsaprouter.sh.j2 |

SAProuter SAPROUTTAB template
---

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_saprouttab_template | | SAPROUTTAB.any.j2 |

Location of original utility SAPCAR
---

The SAPCAR utility is used to unarchive SAProuter (and other) SAP archives.

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_deployment_sapcar_local_dir  | | none |
| saprouter_deployment_sapcar_remote_dir | | none |
| saprouter_deployment_bundle_sapcar_file       | | SAPCAR_1115-70006178.EXE |

Variables `saprouter_deployment_sapcar_local_dir` and `saprouter_deployment_sapcar_remote_dir` are mutually exclusive.
If SAPCAR location is not specified then location of original archives for SAProuter will be used
(`saprouter_deployment_bundle_local_dir`/`saprouter_deployment_bundle_remote_dir`).
