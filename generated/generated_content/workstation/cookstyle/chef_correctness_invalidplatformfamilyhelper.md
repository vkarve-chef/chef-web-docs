+++
title = "InvalidPlatformFamilyHelper"

+++

<!-- This content is automatically generated. See https://github.com/chef/chef-web-docs/blob/main/generated/README.md -->

The department is: `InvalidPlatformFamilyHelper`

The full name of the cop is: `Chef/Correctness/InvalidPlatformFamilyHelper`

| Enabled by default | Supports autocorrection | Target Chef Version |
| --- | --- | --- |
| Enabled | Yes | All Versions |

Pass valid platform families to the `platform_family?` helper. See [Infra Language: Platform Family](https://docs.chef.io/infra_language/checking_platforms/#platform_family-values) for a complete list of platform families.

## Examples


#### incorrect

```ruby
platform_family?('redhat')
platform_family?('sles')

#### incorrect

```ruby
platform_family?('rhel')
platform_family?('suse')
```

## Configurable attributes

<table>
<tbody><tr>
<th>Name</th>
<th>Default value</th>
<th>Configurable values</th>
</tr>
<tr>
<td style="text-align:center">Version Added</td>
<td style="text-align:center">5.15.0</td>
<td style="text-align:center">String</td>
</tr>
<tr><td style="text-align:center">Include</td>
<td style="text-align:center"><ul>
</ul>
</td>
<td style="text-align:center">Array</td>
</tr></tbody></table>
