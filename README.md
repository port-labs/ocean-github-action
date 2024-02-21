<!-- action-docs-header action="action.yml" -->

<!-- action-docs-header action="action.yml" -->

<img align="right" width="100" height="74" src="https://user-images.githubusercontent.com/8277210/183290025-d7b24277-dfb4-4ce1-bece-7fe0ecd5efd4.svg" />

# Ocean Sail GitHub Action - by getPort.io

[![Slack](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)](https://www.getport.io/community)

<!-- action-docs-description action="action.yml" -->
## Description

Runs the Ocean Sail command for a specific type of integration
<!-- action-docs-description action="action.yml" -->

The `sail` command is part of the Ocean framework and is used to run integrations.

Read more about the Ocean framework [here](https://ocean.getport.io/)

<!-- action-docs-inputs action="action.yml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `type` | <p>The type of the integration to run</p> | `true` | `""` |
| `identifier` | <p>The identifier of the integration to run</p> | `false` | `""` |
| `port_client_id` | <p>The Port client id</p> | `true` | `""` |
| `port_client_secret` | <p>The Port client secret</p> | `true` | `""` |
| `initialize_port_resources` | <p>Should ocean try to create the default blueprints, pages &amp; integration config for the integration</p> | `false` | `true` |
| `config` | <p>The configuration for the integration</p> | `false` | `""` |
| `platform` | <p>The platform to run the integration on</p> | `false` | `linux/amd64` |
| `image` | <p>The image to run the integration from</p> | `false` | `""` |
| `version` | <p>The version of the integration to run</p> | `false` | `latest` |
<!-- action-docs-inputs action="action.yml" -->

<!-- action-docs-outputs action="action.yml" -->
## Outputs

| name | description |
| --- | --- |
| `exit_code` | <p>The exit code of the Ocean Sail command</p> |
<!-- action-docs-outputs action="action.yml" -->

## Available integration types

All available integration types are listed in the [Ocean integrations library](https://ocean.getport.io/integrations-library/) and can also be found in the data sources menu in the Port UI.

## Example usage

```yaml
- uses: port-labs/ocean-sail@v1
  with:
    type: 'jira'
    port_client_id: ${{ secrets.PORT_CLIENT_ID }}
    port_client_secret: ${{ secrets.PORT_CLIENT_SECRET }}
    config: |
      jira_host: ${{ secrets.JIRA_HOST }}
      atlassian_user_email: ${{ secrets.ATLASSIAN_USER_EMAIL }}
      atlassian_user_token: ${{ secrets.ATLASSIAN_USER_TOKEN }}
```