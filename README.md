# Galaxy K8S Boot GitHub Action

Installs Kubernetes and Galaxy onto the job runner using the Ansible Playbook from the [galaxy-k8s-boot](https://github.com/galaxyproject/galaxy-k8s-boot) project.
## TL;DR
```yaml
jobs:
  my-job:
    steps:
    - uses: ksuderman/github-action-galaxy-k8s@v1
      with:
        api-key: top_secret
        values_file: values.yml
```
After the action completes all pods will be running and the Galaxy instance will be available at `http://localhost`. The kubeconfig file will be available as `$HOME/.kube/config` for any subsequent steps that want to use `kubectl` commands.

## Inputs

The GitHub action supports the same set of input values as the `galaxy-k8s-boot` playbook:

- **playbook-repo**:<br/>The repository containing the playbook to run. Default: `galaxyproject/galaxy-k8s-boot`.
- **playbook-ref**:<br/>The branch, tag, or commit to checkout. Default: `master`.
- **reserved-cores**:<br/>Number of cores to reserve for the system. Default: `2`.
- **reserved-mem-gb**:<br/>Amount of memory to reserve for the system in GB. Default: `6`.
- **api-key**:<br/>API key to use for the Galaxy instance. Default: `changeme`.
- **values_file**:<br/>Values file to use for the Galaxy Helm chart. Optional.



