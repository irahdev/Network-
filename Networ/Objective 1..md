### [Types of personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#types-of-personal-access-tokens)

GitHub currently supports two types of personal access tokens: fine-grained personal access tokens and personal access tokens (classic). GitHub recommends that you use fine-grained personal access tokens instead of personal access tokens (classic) whenever possible.

Both fine-grained personal access tokens and personal access tokens (classic) are tied to the user who generated them and will become inactive if the user loses access to the resource.

Organization owners can set a policy to restrict the access of personal access tokens (classic) to their organization. For more information, see [Setting a personal access token policy for your organization](https://docs.github.com/en/organizations/managing-programmatic-access-to-your-organization/setting-a-personal-access-token-policy-for-your-organization#restricting-access-by-personal-access-tokens).

#### [Fine-grained personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#fine-grained-personal-access-tokens)

Fine-grained personal access tokens have several security advantages over personal access tokens (classic):

- Each token can only access resources owned by a single user or organization.
- Each token can only access specific repositories.
- Each token is granted specific permissions, which offer more control than the scopes granted to personal access tokens (classic).
- Organization owners can require approval for any fine-grained personal access tokens that can access resources in the organization.

#### [Personal access tokens (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#personal-access-tokens-classic)

Personal access tokens (classic) are less secure. However, some features currently will only work with personal access tokens (classic):

- Only personal access tokens (classic) have write access for public repositories that are not owned by you or an organization that you are not a member of.
- Outside collaborators can only use personal access tokens (classic) to access organization repositories that they are a collaborator on.
- A few REST API endpoints are only available with a personal access tokens (classic). To check whether an endpoint also supports fine-grained personal access tokens, see the documentation for that endpoint, or see [Endpoints available for fine-grained personal access tokens](https://docs.github.com/en/rest/overview/endpoints-available-for-fine-grained-personal-access-tokens).

If you choose to use a personal access token (classic), keep in mind that it will grant access to all repositories within the organizations that you have access to, as well as all personal repositories in your personal account.

As a security precaution, GitHub automatically removes personal access tokens that haven't been used in a year. To provide additional security, we highly recommend adding an expiration to your personal access tokens.

### [Keeping your personal access tokens secure](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#keeping-your-personal-access-tokens-secure)

Personal access tokens are like passwords, and they share the same inherent security risks. Before creating a new personal access token, consider if there is a more secure method of authentication available to you:

- To access GitHub from the command line, you can use [GitHub CLI](https://docs.github.com/en/github-cli/github-cli/about-github-cli) or [Git Credential Manager](https://github.com/GitCredentialManager/git-credential-manager/blob/main/README.md) instead of creating a personal access token.
- When using a personal access token in a GitHub Actions workflow, consider whether you can use the built-in `GITHUB_TOKEN` instead. For more information, see [Automatic token authentication](https://docs.github.com/en/actions/security-guides/automatic-token-authentication).

If these options are not possible, and you must create a personal access token, consider using another CLI service to store your token securely.

When using a personal access token in a script, you can store your token as a secret and run your script through GitHub Actions. For more information, see [Using secrets in GitHub Actions](https://docs.github.com/en/actions/security-guides/encrypted-secrets). You can also store your token as a Codespaces secret and run your script in Codespaces. For more information, see [Managing your account-specific secrets for GitHub Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-encrypted-secrets-for-your-codespaces).

For more information about best practices, see [Keeping your API credentials secure](https://docs.github.com/en/rest/overview/keeping-your-api-credentials-secure).