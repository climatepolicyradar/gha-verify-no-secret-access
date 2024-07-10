# Verfiy No Secret Access

Verify that the workflow doesn't have access to the specified secret.

## Description

Verify that the workflow doesn't have access to the specified secret. This can be very useful for throwing an error should a flow authored by dependabot for example have access to a secret like an iam credential.

## Usage

### Basic

```yaml
- name: Retag an image in Amazon ECR
  id: retag-ecr
  uses: climatepolicyradar/gha-verify-no-secret-access@v0
  with:
    repository-name: example
    source-tag: latest
    destination-tag: release
```

### Specify full version

```yaml
- name: Retag an image in Amazon ECR
  id: retag-ecr
  uses: climatepolicyradar/gha-verify-no-secret-access@v0.1.0
  with:
    repository-name: example
    source-tag: latest
    destination-tag: release
```

## Inputs

| Name            | Description                             | Default | Required |
| --------------- | --------------------------------------- | ------- | :------: |
| repo_secret     | The secret to verify no access for.     | n/a     |   yes    |

## Developer Guide

### Requirements

- [GNU Make](https://www.gnu.org/software/make/)
- [GitHub CLI](https://cli.github.com/)

### Update documents

Update usage automatically in [README.md](/README.md).

```shell
make docs
```

### Release

#### 1. Bump up to a new version

Run the following command to bump up.

```shell
make bump
```

This command will execute the following steps:

1. Update [VERSION](/VERSION)
2. Update [README.md](/README.md)
3. Commit and push
4. Create a pull request
5. Open the web browser automatically for reviewing pull request

Then review and merge, so the release is ready to go.

#### 2. Create a new GitHub Release

Run the following command to create a new release.

```shell
make release
```

This command will execute the following steps:

1. Push tag
2. Create a new GitHub Release as a draft
3. Open the web browser automatically for editing GitHub Release

#### 3. Publish actions in GitHub Marketplace

Edit to publicize the GitHub Release.

1. Click the edit icon on the right side of the page
2. Edit the release notes
3. Click `Publish release`

Then, the new version are published in GitHub Marketplace.
Finally, we can use the new version! :tada:

## References

- [Retagging an image - Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-retag.html)

## License

Apache 2 Licensed. See LICENSE for full details.
