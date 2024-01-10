# ensure_certmanager_state

[![Validate infrastructure as code](https://github.com/garliclabs/ansible_role_ensure_certmanager_state/actions/workflows/validation.yml/badge.svg)](https://github.com/garliclabs/ansible_role_ensure_certmanager_state/actions/workflows/validation.yml)

Manages the state of a certmanager deployment in your kubernetes cluster via helm.
This role does not create custom CRDs for certmanager, for this please take a look on [ansible_role_configure_certmanager](https://github.com/GarlicLabs/ansible_role_configure_certmanager)

## Requirements

Kubernetes, Helm

## Role Variables

```bash
certmanager_kubeconfig
certmanager_state
certmanager_namespace
certmanager_chart_version
```

**certmanager_kubeconfig:** Specify the path to your kubeconfig, so the role can deploy to your kubernetes cluster
**certmanager_state:** State of the certmanager deployment can be either present or absent
**certmanager_namespace:** Namespace in that the certmanager will be deployed
**certmanager_chart_version:** Version of the chart that will be deployed

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
