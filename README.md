# GitHub Actions

## Azure Credentials

- az account show
- az ad sp create-for-rbac --name GitHubActions --role Contributor --scopes /subscriptions/{sub_id} --sdk-auth

## Deploy Arm Templates

- [Azure CLI Action](https://github.com/marketplace/actions/azure-cli-action)
- [Deploy ARM Template](https://github.com/marketplace/actions/deploy-azure-resource-manager-arm-template)
- [Azure Vault Action](https://github.com/marketplace/actions/enhanced-env-azure-key-vault-get-secrets)

## Deployment Modes

- Incremental (default): ARM will not do anything with other resources that exist in target resource group that are not defined inside of template. ARM will only create or modify resources that are defined in the template being deployed.
- Complete: if the resource is not defined in the template file you are deploying, ARM will delete that resource

## GitHub Secrets

- Uses a libsodium sealed box to encrypt secrets
  - when you create a secret, it is encrypted before it reaches GitHub to be stored
  - and remains encrypted until you use the secret in a workflow
- Automatically redacts secrets printed to the log
- To provide an action with a secret, use the secrets context
  - ${{ secrets.TopSecretSecret }}

## Note

- GitHub environments only available for public repos

## Resources

- [GitHub Actions Marketplace](https://github.com/marketplace)
