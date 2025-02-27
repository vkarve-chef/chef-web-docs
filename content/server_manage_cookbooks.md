+++
title = "Manage Cookbooks"
draft = false
gh_repo = "chef-web-docs"
robots = "noindex"
aliases = ["/server_manage_cookbooks.html"]
product = []

[menu]
  [menu.legacy]
    title = "Cookbooks"
    identifier = "legacy/manage/server_manage_cookbooks.md Cookbooks"
    parent = "legacy/manage"
+++

{{< chef_automate_mark >}}

{{< warning >}}

{{< readfile file="content/reusable/md/EOL_manage.md" >}}

{{< /warning >}}

{{< note >}}

This topic is about using the Chef management console to manage
cookbooks.

{{< /note >}}

{{< readfile file="content/reusable/md/cookbooks_summary.md" >}}

## Manage

Cookbooks can be viewed from the Chef management console web user
interface. Cookbooks are managed using knife.

### View Cookbook Details

To view cookbook details:

1. Open the Chef management console.

2. Click **Policy**.

3. Click **Cookbooks**.

4. Select a cookbook.

5. Click the **Details** tab:

    ![image](/images/step_manage_webui_policy_cookbook_view_details.png)

## Cookbook Files

A cookbook can contain the following types of files:

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<thead>
<tr class="header">
<th>File Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Attributes</td>
<td>{{< readfile file="content/reusable/md/cookbooks_attribute.md" >}}</td>
</tr>
<tr>
<td>Files</td>
<td>{{< readfile file="content/reusable/md/resource_cookbook_file_summary.md" >}}</td>
</tr>
<tr>
<td>Libraries</td>
<td>{{< readfile file="content/reusable/md/libraries_summary.md" >}}</td>
</tr>
<tr>
<td>Recipes</td>
<td>{{< readfile file="content/reusable/md/cookbooks_recipe.md" >}}</td>
</tr>
<tr>
<td>Resources</td>
<td>{{< readfile file="content/reusable/md/resources_common.md" >}}</td>
</tr>
<tr>
<td>Templates</td>
<td>{{< readfile file="content/reusable/md/template.md" >}}</td>
</tr>
</tbody>
</table>

All of the file types that are part of any cookbook uploaded to the Chef
Infra Server are visible from the Chef management console.

### Download File

To download a file that is located in a cookbook:

1. Open the Chef management console.

2. Click **Policy**.

3. Click **Cookbooks**.

4. Select the file type: **Attributes**, **Definitions**, **Files**,
    **Recipes**, **Templates**, or **Root Files**.

5. Select a file.

6. Click **Download File**:

    ![image](/images/step_manage_webui_policy_cookbook_download.png)

7. Specify the location to which the file should be saved.

### View a File

To view a cookbook file:

1. Open the Chef management console.

2. Click **Policy**.

3. Click **Cookbooks**.

4. Select a cookbook.

5. Click the **Content** tab.

6. Select the file type: **Attributes**, **Definitions**, **Files**,
    **Recipes**, **Templates**, or **Root Files**.

7. Select a file:

    ![image](/images/step_manage_webui_policy_cookbook_file_view.png)

## Permissions

{{% chef-server/server_rbac_permissions %}}

{{% chef-server/server_rbac_permissions_object %}}

### Set

To set permissions list for a cookbook object:

1. Open the Chef management console.
2. Click **Policy**.
3. Click **Cookbooks**.
4. Select a cookbook.
5. Click the **Permissions** tab.
6. For each group listed under **Name**, select or de-select the
    **Read**, **Update**, **Delete**, and **Grant** permissions.

### Update

To update the permissions list for a cookbook object:

1. Open the Chef management console.
2. Click **Policy**.
3. Click **Cookbooks**.
4. Select a cookbook.
5. Click the **Permissions** tab.
6. Click the **+ Add** button and enter the name of the user or group
    to be added.
7. Select or de-select **Read**, **Update**, **Delete**, and **Grant**
    to update the permissions list for the user or group.

### View

To view permissions for a cookbook object:

1. Open the Chef management console.
2. Click **Policy**.
3. Click **Cookbooks**.
4. Select a cookbook.
5. Click the **Permissions** tab.
6. Set the appropriate permissions: **Delete**, **Grant**, **Read**,
    and/or **Update**.
