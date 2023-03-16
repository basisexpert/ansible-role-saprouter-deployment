ansible-role-saprouter-deployment
===

Location of original utility SAPCAR

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_deployment_bundle_sapcar_local_dir  | | none |
| saprouter_deployment_bundle_sapcar_remote_dir | | none |
| saprouter_deployment_bundle_sapcar_file       | | SAPCAR_1115-70006178.EXE |

Location of original archives for SAProuter deployment

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_deployment_bundle_local_dir | | files/saprouter_deployment_bundle |
| saprouter_deployment_bundle_remote_dir | | |
| saprouter_deployment_bundle_saprouter_sar_file | | saprouter_1011-80003478.sar |
| saprouter_deployment_bundle_sapcryptolib_sar_file | | SAPCRYPTOLIBP_8544-20011697.SAR |

SAProuter's instance deployment parameters

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_deployment_sid | | R99 |
| saprouter_deployment_instance_number | | '99' |
| saprouter_deployment_instance_name | | "R{{ saprouter_deployment_instance_number }}" |
| saprouter_deployment_user_name | | "{{ saprouter_deployment_sid | lower }}adm" |
| saprouter_deployment_user_shell | | /bin/bash |
| saprouter_deployment_user_uid | | |
| saprouter_deployment_group_sapsys_gid | | |
| saprouter_deployment_src_dir | | "/usr/sap/src/{{ saprouter_deployment_sid }}" |
| saprouter_regenerate_saprouttab_enabled | | false |

SAProuter start/stop script templates

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_start_script_template | | startsaprouter.sh.j2 |
| saprouter_stop_script_template | | stopsaprouter.sh.j2 |

SAProuter SAPROUTTAB template

| Variable | Description | Default |
| --- | --- | --- |
| saprouter_saprouttab_template | | SAPROUTTAB.any.j2 |
