---
wts:
  title: 12 - 实现 Azure 密钥保管库（5 分钟）
  module: 'Module 04: Describe general security and network security features'
---
# <a name="12---implement-azure-key-vault-5-min"></a>12 - 实现 Azure 密钥保管库（5 分钟）

在本演练中，我们将创建一个 Azure 密钥保管库，然后在该密钥保管库中创建一个密码机密，从而提供安全存储且集中管理的密码，以用于应用程序。

# <a name="task-1-create-an-azure-key-vault"></a>任务 1：创建 Azure 密钥保管库 

1. 登录 [Azure 门户](https://portal.azure.com)。

2. 在“所有服务”边栏选项卡中，搜索并选择“密钥保管库”，然后选择“+ 添加 + 新建 + 创建”** **。

3. Configure the key vault (replace <bpt id="p1">**</bpt>xxxx<ept id="p1">**</ept> in the name of the key vault with letters and digits such that the name is globally unique). Leave the defaults for everything else.

    | 设置 | 值 | 
    | --- | --- |
    | 订阅 | 使用提供的默认值 |
    | 资源组 | **新建资源组** |
    | 密钥保管库名称 | keyvaulttestxxx |
    | 位置 | **美国东部** |
    | 定价层 | **标准** |
    
    注意替换“xxxx”以查找唯一名称 。
4. 单击“查看 + 创建”，然后单击“创建” 。 

5. Once the new key vault is provisioned, click <bpt id="p1">**</bpt>Go to resource<ept id="p1">**</ept>. Or you can locate your new key vault by searching for it. 

6. Click on the key vault <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> tab and take note of the <bpt id="p2">**</bpt>Vault URI<ept id="p2">**</ept>. Applications that use your vault through the REST APIs will need this URI.

7. Take a moment to browse through some of the other key vault options. Under <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> review <bpt id="p2">**</bpt>Keys<ept id="p2">**</ept>, <bpt id="p3">**</bpt>Secrets<ept id="p3">**</ept>, <bpt id="p4">**</bpt>Certificates<ept id="p4">**</ept>, <bpt id="p5">**</bpt>Access Policies<ept id="p5">**</ept>, <bpt id="p6">**</bpt>Firewalls and virtual networks<ept id="p6">**</ept>.

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Your Azure account is the only one authorized to perform operations on this new vault. You can modify this if you wish in the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> and then the <bpt id="p2">**</bpt>Access policies<ept id="p2">**</ept> section.

# <a name="task-2-add-a-secret-to-the-key-vault"></a>任务 2：向密钥保管库添加机密
        
在此任务中，我们将向密钥保管库添加密码。 

1. 在“设置”下，单击“机密”，然后单击“+ 生成/导入”  。

2. Configure the secret. Leave the other values at their defaults. Notice you can set an activation and expiration date. Notice you can also disable the secret.

    | 设置 | 值 | 
    | --- | --- |
    | 上传选项 | **手动** |
    | 名称 | ExamplePassword |
    | 值 | hVFkk96 |

3. 单击“创建”。

4. 成功创建机密后，单击“ExamplePassword”，请注意其状态为“已启用” 

5. Select the secret you just created, note the the <bpt id="p1">**</bpt>Secret Identifier<ept id="p1">**</ept>. This is the url value that you can now use with applications. It provides a centrally managed and securely stored password. 

6. 单击按钮“显示机密值”，显示你先前指定的密码。


配置密钥保管库（将密钥保管库名称中的 xxxx 替换为字母和数字，使该名称在全局范围内唯一）。

所有其他设置均保留默认值。
