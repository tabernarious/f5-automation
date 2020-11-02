Could this be remedied by updating the `Setup provider and variables` task in `tasks/main.yml` to:

```
  set_fact:
    provider: "{{ provider }}"
    atc_declaration: "{{ atc_declaration|default(omit) }}"
    atc_declaration_url: "{{ atc_declaration_url|default(omit) }}"
    atc_declaration_file: "{{ atc_declaration_file|default(omit) }}"
    atc_tenant: "{{ as3_tenant|default(omit) }}"
    atc_show: "{{ as3_show|default(omit) }}"
    atc_show_hash: "{{ as3_showhash|default(false) }}"
```