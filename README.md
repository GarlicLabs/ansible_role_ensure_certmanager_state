# ensure_certmanager_state

[![Validate infrastructure as code](https://github.com/garliclabs/ansible_role_ensure_certmanager_state/actions/workflows/validation.yml/badge.svg)](https://github.com/garliclabs/ansible_role_ensure_certmanager_state/actions/workflows/validation.yml)

Manages the state of a certmanager deployment in your kubernetes cluster via helm.
This role does not create custom CRDs for certmanager, for this please take a look on [ansible_role_configure_certmanager](https://github.com/GarlicLabs/ansible_role_configure_certmanager)

## Requirements

Kubernetes, Helm

## Role Variables

```bash
certmanager_kubeconfig: "{{ undef(hint='Specify your kubeconfig location') }}"
certmanager_state: present
certmanager_namespace: default
certmanager_chart_version: v1.13.3
```

## Development

### Testing

* Create venv: `python3 -m venv ./venv`
* Install pip requirements: `venv/bin/pip install -r pip_requirements.txt`
* Execute tests `venv/bin/molecule test`

### Linting & static security analyser

Both the linter and the static security analyser are running on each push on the github actions pipeline.  

* As linter [ansible-lint](https://ansible.readthedocs.io/projects/lint/) is used. For installation documentation see [ansible lint installing](https://ansible.readthedocs.io/projects/lint/)
  * Just run `ansible-lint`

* To check if there are any passwords, tokens... hardcoded, [kics](https://kics.io/index.html) is used to ensure a secure IaC repository.  
  * Run it locally `docker run -t -v $PWD:/path checkmarx/kics:latest scan -p /path -o "/path/"`

## License

GNU General Public License version 3
