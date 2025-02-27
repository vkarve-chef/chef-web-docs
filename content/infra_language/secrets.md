+++
title = "Chef Infra Language: Secrets"
draft = false

gh_repo = "chef-web-docs"

[menu]
  [menu.infra]
    title = "Secrets Management Integrations"
    identifier = "chef_infra/infra_language/secrets.md Secrets Management Integrations"
    parent = "chef_infra/infra_language"
+++

The Secrets Management Integration helper is a beta feature starting in Chef Infra Client 17.5 and became a fully supported feature in Chef Infra Client 18. This helper allows you to access secrets from the following secrets management systems within your Infra recipes or resources:

- AWS Secrets Manager
- Akeyless Vault
- Azure Key Vault
- HashiCorp Vault

## Secrets Manager Support

### AWS Secrets Manager

The secrets helper supports fetching secrets from AWS Secrets Manager from IAM roles applied to instances.

#### Fetching an AWS Secrets Manager secret

```ruby
secret(name: 'test1', service: :aws_secrets_manager)
```

#### Specifying the AWS Region containing the secret

```ruby
secret(name: 'test1', service: :aws_secrets_manager, config: { region: 'us-west-2' })
```

### Akeyless Vault

The secrets helper supports fetching secrets from Akeyless Vault using Akeyless' access key and access id.

#### Fetching Secrets From Akeyless Vault Using Access Key/ID

```ruby
secret(name: '/secret/data/my_secret',
       service: :akeyless_vault,
       config: {
         access_key: '12345678910=',
         access_id: 'p-12345678910'
      })
```

### Azure Key Vault

The secrets helper supports fetching secrets from Akeyless Vault using Akeyless' access key and access id.

#### Fetching Secrets From Azure Key Vault

```ruby
secret(name: 'vault-name/test-secret-1', service: :azure_key_vault)
```

#### Fetching a specific version of an Azure Key Vault secret

```ruby
secret(name: 'vault-name/test1', version: 'v1', service: :azure_key_vault)
```

### HashiCorp Vault

#### Fetching Secrets From HashiCorp Vault Using AWS IAM

```ruby
secret(name: 'secret/example',
      service: :hashi_vault,
      config: {
        vault_addr: 'vault.example.com',
        role_name: 'example-role'
      })
```

#### Fetching Secrets From HashiCorp Vault Using Tokens

```ruby
secret(name: 'secret/example',
      service: :hashi_vault,
      config: {
        vault_addr: 'vault.example.com',
        auth_method: :token,
        token: '123456'
      })
```

#### Fetching Secrets From HashiCorp Vault Using AppRole Authentication

Fetching secret data using an AppRole ID and an associated AppRole Secret ID:

```ruby
secret(name: 'secret/example',
      service: :hashi_vault,
      config: {
        vault_addr: 'vault.example.com',
        auth_method: :approle,
        approle_id: "11111111-abcd-1111-abcd-111111111111",
        approle_secret_id: "22222222-abcd-2222-abcd-222222222222"
      })
```

Fetching secret data using a token and an AppRole name creates a Secret ID associated with that AppRole:

```ruby
secret(name: 'secret/example',
      service: :hashi_vault,
      config: {
        vault_addr: 'vault.example.com',
        auth_method: :approle,
        approle_name: "my-approle",
        token: '123456'
      })
```

## Using in Cookbooks

The secrets helper returns a text string, so it can be used anywhere in Chef Infra where you might hard code a value or access a value from a data bag.

### Writing a Secret To a File

```ruby
file '/home/ubuntu/aws-secret' do
  content secret(name: 'test1', service: :aws_secrets_manager)
end
```

### Passing a Secret to a Template

```ruby
template '/etc/my_fancy_service/my_fancy_service.conf' do
  source 'config.erb'
  variables(
    db_token: secret(name: 'db_token', service: :aws_secrets_manager)
  )
end
```
