# openshift install-config.yaml schema

This repository contains an unofficial JSON validator for OpenShift's `install-config.yaml` configuration file.

To use in your editor:
* Install [yaml-language-server](https://github.com/redhat-developer/yaml-language-server)
* Add the schema hint at the top of the file, as shown in this example:

```yaml
# yaml-language-server: $schema=https://raw.githubusercontent.com/pierreprinetti/openshift-installconfig-schema/release-4.16/installconfig.schema.json
apiVersion: v1
// [...]
```
