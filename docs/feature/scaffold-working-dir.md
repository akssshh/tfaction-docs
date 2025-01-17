---
sidebar_position: 350
---

# Scaffold working directory by GitHub Actions `workflow_dispatch` event

Execute GitHub Actions Workflow manually.

![image](https://user-images.githubusercontent.com/13323303/150027710-19ce0659-4a7a-490d-ad7b-bf77e409099f.png)

Then a pull request would be created.

![image](https://user-images.githubusercontent.com/13323303/151699745-b8743536-7e54-41e1-8f8e-73fdf296fef4.png)

Compared with executing commands at the localhost, GitHub Actions has the following merits.

* GitHub Actions doesn't depend on you local environment
  * You don't have to install tools at local
  * You can avoid the trouble due to the difference of local environment
  * GitHub Actions log is useful for trouble shooting

## :bulb: Skip creating pull requests

If you don't want to create pull requests by GitHub App, please see [Support skipping creating pull requests](skip-creating-pr.md).

## :bulb: Skip creating aqua.yaml and adding packages

tfaction >= v0.5.25

[#910](https://github.com/suzuki-shunsuke/tfaction/pull/910)

By default scaffold-working-directory creates `aqua.yaml` and add some packages.

```sh
aqua init
aqua g -i open-policy-agent/conftest terraform-linters/tflint aquasecurity/tfsec hashicorp/terraform
```

You can skip this.

tfaction-root.yaml

```yaml
scaffold_working_directory:
  skip_adding_aqua_packages: true
```

By skipping this, you can configure packages and their versions in your template or you can also manage them in repository root's aqua.yaml.
