此版本的 GitHub Enterprise 将停止服务 此版本的 GitHub Enterprise 已停止服务 2019-07-12. 即使出现严重安全问题，也不会发布补丁。要获得更好的性能、更高的安全性和全新功能，[请升级到 GitHub Enterprise 的最新版本](https://docs.github.com/enterprise/admin/guides/installation/upgrading-github-enterprise/)。 要获取有关升级的帮助，[请联系 GitHub Enterprise 支持部门](https://enterprise.github.com/support)。

删除仓库
如果您是组织所有者或拥有仓库或分叉的管理员权限，可删除任何仓库或分叉。 删除分叉仓库不会删除上游仓库。

只有拥有组织所有者权限或仓库管理员权限的成员才能 删除组织仓库。 如果已禁用 Allow members to delete or transfer repositories for this organization（允许成员删除或转让此组织的仓库），仅组织所有者可删除组织仓库。 更多信息请参阅“[组织的仓库权限级别](https://docs.github.com/cn/enterprise/2.14/user/articles/repository-permission-levels-for-an-organization)”。

警告：以下步骤将永久性删除仓库、wiki、issue 和注释。 此操作必须完成。

请同时记住进行以下内容：

删除私有仓库将删除其所有分叉。
删除公共仓库不会删除其分叉。
在 GitHub Enterprise 上，导航到仓库的主页面。

在仓库名称下，单击  Settings（设置）。