# openshift install-config.yaml schema

This repository contains an unofficial JSON validator for OpenShift's `install-config.yaml` configuration file.

To use in your editor:
* Install [yaml-language-server](https://github.com/redhat-developer/yaml-language-server)
* Add the schema hint at the top of the file:

```yaml
# yaml-language-server: $schema=https://raw.githubusercontent.com/pierreprinetti/openshift-installconfig-schema/release-4.16/installconfig.schema.json
```

## Example

```yaml
# yaml-language-server: $schema=https://raw.githubusercontent.com/pierreprinetti/openshift-installconfig-schema/release-4.16/installconfig.schema.json
apiVersion: v1
featureSet: 'CustomNoUpgrade'
featureGates: ['ClusterAPIInstall=true']
baseDomain: ocp.example.com
compute:
- name: worker
  platform:
    openstack:
      serverGroupPolicy: soft-anti-affinity
      type: ocp.worker
      rootVolume:
        size: 80
        type: tripleo
  replicas: 3
controlPlane:
  name: master
  platform:
    openstack:
      serverGroupPolicy: anti-affinity
      type: ocp.master
      rootVolume:
        size: 80
        type: tripleo
  replicas: 3
metadata:
  name: ocp1
platform:
  openstack:
    cloud: openstack
    externalNetwork: external
publish: External
pullSecret: |
  ${PULL_SECRET}
sshKey: |
  ${SSH_PUB_KEY}
```
