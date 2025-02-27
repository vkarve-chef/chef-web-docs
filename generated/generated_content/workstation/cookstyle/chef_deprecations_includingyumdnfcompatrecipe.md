+++
title = "IncludingYumDNFCompatRecipe"

+++

<!-- This content is automatically generated. See https://github.com/chef/chef-web-docs/blob/main/generated/README.md -->

The department is: `IncludingYumDNFCompatRecipe`

The full name of the cop is: `Chef/Deprecations/IncludingYumDNFCompatRecipe`

| Enabled by default | Supports autocorrection | Target Chef Version |
| --- | --- | --- |
| Enabled | Yes | All Versions |

Don't include the deprecated yum DNF compatibility recipe, which is no longer necessary
as Chef Infra Client includes DNF package support

## Examples


#### incorrect

```ruby
include_recipe 'yum::dnf_yum_compat'
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
<td style="text-align:center">5.3.0</td>
<td style="text-align:center">String</td>
</tr>
<tr><td style="text-align:center">Include</td>
<td style="text-align:center"><ul>
</ul>
</td>
<td style="text-align:center">Array</td>
</tr></tbody></table>
