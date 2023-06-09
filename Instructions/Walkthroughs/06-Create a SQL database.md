---
wts:
  title: 06 - 创建 SQL 数据库（5 分钟）
  module: Module 02 - Core Azure Services (Workloads)
---

# <a name="06---create-a-sql-database-5-min"></a>06 - 创建 SQL 数据库（5 分钟）

在本演练中，我们将在 Azure 中创建一个 SQL 数据库，然后查询该数据库中的数据。

# <a name="task-1-create-the-database"></a>任务 1：创建数据库 

在此任务中，我们将基于“AdventureWorksLT”示例数据库创建 SQL 数据库。 

1. 通过 [ **https://portal.azure.com** ](https://portal.azure.com) 登录到 Azure 门户。

2. 从“所有服务”边栏选项卡，搜索并选择“SQL 数据库”，然后单击“+ 添加、+ 创建、+ 新建”  。 

3. 在“基本”选项卡上，填写此信息。  

    | 设置 | 值 | 
    | --- | --- |
    | 订阅 | 使用提供的默认值 |
    | 资源组 | **新建资源组** |
    | 数据库名称| **db1** | 
    | 服务器 | 选择“新建”（右侧会打开一个新的侧边栏）|
    | 服务器名称 | **sqlserverxxxx**（必须是唯一的） | 
    | 位置 | **（美国）美国东部** |
    | 身份验证方法 | 使用 SQL 身份验证 |
    | 服务器管理员登录名 | **sqluser** |
    | Password | **Pa$$w0rd1234** |
    | 单击  | **正常** |

   ![“服务器”窗格和“新建服务器”窗格的屏幕截图，其中已按照表格填充字段，并突出显示了“查看 + 创建”和“确定”按钮。](../images/0501.png)

4. 在“网络”选项卡，配置以下设置（其他设置保留为默认值） 

    | 设置 | 值 | 
    | --- | --- |
    | 连接方法 | **公共终结点** |    
    | 允许 Azure 服务和资源访问此服务器 | **是** |
    | 添加当前客户端 IP 地址 | 否 |
    
   ![“创建 SQL 数据库”边栏选项卡的“网络”选项卡的屏幕截图，其中已根据表选择了设置，并且突出显示了“查看 + 创建”按钮。](../images/0501b.png)

5. 在“安全”选项卡上。 

    | 设置 | Value | 
    | --- | --- |
    | Microsoft Defender for SQL| 以后再说 |
    
6. 前往“其他设置”选项卡。我们将使用 AdventureWorksLT 示例数据库。

    | 设置 | 值 | 
    | --- | --- |
    | 使用现有数据 | **示例** |

    ![“创建 SQL 数据库”边栏选项卡的“其他设置”选项卡的屏幕截图，其中已根据表选择了设置，并且突出显示了“查看 + 创建”按钮。](../images/0501c.png)

7. 单击“查看 + 创建”，然后单击“创建”以部署和预配资源组、服务器和数据库 。 部署大约需要 2 到 5 分钟。


# <a name="task-2-test-the-database"></a>任务 2：测试数据库。

在此任务中，我们将配置 SQL server 并运行 SQL 查询。 

1. 部署完成后，在“部署”边栏选项卡上单击“转到资源”。 此外，在“所有资源”边栏选项卡中，搜索并选择“数据库”，然后选择“SQL 数据库”并确保已创建新数据库  。 可能需要刷新页面。

    ![刚刚部署的 SQL 数据库和服务器的屏幕截图。](../images/0502.png)

2. 单击表示创建的 SQL 数据库的 db1 条目。 在 db1 边栏选项卡中，单击“查询编辑器(预览)”。

3. 以 sqluser 身份登录并输入密码“Pa$$w0rd1234”。

4. 你将无法登录。 仔细阅读错误信息，记下防火墙需要允许的 IP 地址。 

    ![包含 IP 地址错误的查询编辑器登录页的屏幕截图。](../images/0503.png)

5. 返回 db1 边栏选项卡，单击“概述” 。 

    ![“SQL Server”页面的屏幕截图。](../images/0504.png)

6. 从 db1“概述”边栏选项卡中，单击概述屏幕顶部中央的“设置服务器防火墙” 。

7. 单击“+ 添加客户端 IP”（顶部菜单栏），然后添加错误中引用的 IP 地址。 （它可能已自动填充 - 如果你没有将其粘贴到 IP 地址字段）。 务必保存你的更改。 

    ![SQL server 防火墙设置页的屏幕截图，其中突出显示了新 IP 规则。](../images/0506.png)

8. 返回到 SQL 数据库（向左滑动底部切换栏）并单击“查询编辑器(预览)”。 尝试再次以 sqluser 身份登录并输入密码“Pa$$w0rd1234”。 这次应该会成功。 请注意，部署新的防火墙规则可能需要几分钟时间。 

9. 成功登录后，系统将显示查询窗格。 在编辑器窗格中输入以下查询。 

    ```SQL
    SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName
    FROM SalesLT.ProductCategory pc
    JOIN SalesLT.Product p
    ON pc.productcategoryid = p.productcategoryid;
    ```

    ![查询编辑器的屏幕截图，其中包含查询窗格，并显示命令成功执行。](../images/0507.png)

10. 单击“运行”，然后在“结果”窗格中查看查询结果。 查询应会成功运行。

    ![数据库查询编辑器窗格的屏幕截图，其中显示 SQL 代码已成功运行，结果窗格中显示了输出。](../images/0508.png)

恭喜！ 你已在 Azure 中创建了一个 SQL 数据库，并成功查询了该数据库中的数据。

**注意**：为了避免产生额外费用，可以选择删除此资源组。 搜索资源组，单击你的资源组，然后单击“删除资源组”。 验证资源组的名称，然后单击“删除”。 关注“通知”，了解删除操作的进度。
