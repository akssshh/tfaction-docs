---
sidebar_position: 100
---

# Update related pull requests automatically when the base branch is updated

When `terraform plan` or `tfmigrate plan` are run in the target `A`,
tfaction sets a pull request label `A`.

When a pull request of the target `A` is merged and `terraform apply` or `tfmigrate apply` are run in the target `A`,
tfaction updates pull request breanches which have a pull request label `A` by [GitHub API](https://docs.github.com/en/rest/reference/pulls#update-a-pull-request-branch).

![image](https://user-images.githubusercontent.com/13323303/151699327-ba31892c-c4a6-47e7-a944-15fca81dfbfb.png)

By updating pull request branch, the result of CI including uploaded Terraform Plan file is updated.
Otherwise, an uploaded Terraform Plan file becomes stale and it would fail to run `terraform apply`.
